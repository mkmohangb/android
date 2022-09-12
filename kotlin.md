### Kotlin 


3. [More Kotlin Fundamentals](https://developer.android.com/courses/pathways/android-basics-compose-unit-3-pathway-1)
  - Generics
      ```
      class Question<T> (
        val questionText: String,
        val answer: T,
        val difficulty: String
      ) 
  - Enum class
      ```
      enum class Difficulty {
        EASY, MEDIUM, HARD
      }
  - Data class
      ```
      data class Question<T> (
        val questionText: String,
        val answer: T,
        val difficulty: Difficulty
      )
  - Singleton
      ```
      object StudentProgress {
        var total: Int = 10
        var answered: Int = 3
      }
      
      class Quiz {
        companion object StudentProgress {
          var total: Int = 10
          var answered: Int = 3
        }
      }
  - Extend classes with new properties & methods
      ```
      val Quiz.StudentProgress.progressText: String
          get() = "${answered} of ${total} answered"
          
      fun Quiz.StudentProgress.printProgressBar() {
          repeat(Quiz.answered) { print("▓") }
          repeat(Quiz.total - Quiz.answered) { print("▒") }
          println()
          println(Quiz.progressText)
      }
      
  - scope functions to access class properties & methods
      ```
      question1.let {
            println(it.questionText)
            println(it.answer)
            println(it.difficulty)
        }
      Quiz().apply {
           printQuiz()
      }
   [Scope Functions](https://kotlinlang.org/docs/scope-functions.html)
