# Correction du Questionnaire sur JUnit

## Questions à choix unique (en français)

1. Quelle annotation est utilisée pour marquer une méthode comme méthode de test dans JUnit 5 ?
   
   Réponse correcte : b) @Test
   
   Explication : Dans JUnit 5, l'annotation @Test est utilisée pour marquer une méthode comme une méthode de test. Cette annotation indique à JUnit que la méthode doit être exécutée comme un test unitaire.

2. Quelle méthode d'assertion JUnit utiliseriez-vous pour vérifier qu'une valeur est vraie ?
   
   Réponse correcte : b) assertTrue(value)
   
   Explication : La méthode assertTrue() est utilisée dans JUnit pour vérifier qu'une condition est vraie. Elle prend un booléen comme argument et le test échoue si ce booléen est false.

## Questions ouvertes (en anglais)

1. Explain the purpose of the @BeforeEach and @AfterEach annotations in JUnit. How do they differ from @BeforeAll and @AfterAll?

   Réponse modèle : 
   @BeforeEach and @AfterEach are JUnit annotations used to define setup and teardown methods for each test in a test class.

   @BeforeEach:
   - Executed before each test method in the class.
   - Used to set up the test environment (e.g., initializing test fixtures, resetting data).
   - Ensures each test starts with a fresh state.

   @AfterEach:
   - Executed after each test method in the class.
   - Used for cleanup operations (e.g., closing resources, resetting state).
   - Ensures the environment is clean for the next test.

   @BeforeAll and @AfterAll differ in that they are executed once for the entire test class:

   @BeforeAll:
   - Executed once before all test methods in the class.
   - Used for time-consuming setup operations that can be shared by all tests.
   - Must be static unless the test class is annotated with @TestInstance(TestInstance.Lifecycle.PER_CLASS).

   @AfterAll:
   - Executed once after all test methods in the class have been run.
   - Used for final cleanup operations.
   - Also must be static unless using PER_CLASS lifecycle.

   Key differences:
   1. Execution frequency: @BeforeEach and @AfterEach run for each test, while @BeforeAll and @AfterAll run once per test class.
   2. State sharing: @BeforeAll and @AfterAll can set up and tear down shared resources, while @BeforeEach and @AfterEach ensure test isolation.
   3. Method type: @BeforeAll and @AfterAll are typically static methods, while @BeforeEach and @AfterEach are instance methods.

2. What are parameterized tests in JUnit 5 and how do they improve test efficiency? Provide a simple example.

   Réponse modèle:
   Parameterized tests in JUnit 5 allow a test to be executed multiple times with different arguments. They improve test efficiency by:
   1. Reducing code duplication: You write the test logic once and reuse it with different inputs.
   2. Increasing test coverage: It's easier to test multiple scenarios.
   3. Improving readability: The test method clearly shows what inputs are being tested.

   To create a parameterized test, you use the @ParameterizedTest annotation along with a source of arguments.

   Example:

   ```java
   import org.junit.jupiter.params.ParameterizedTest;
   import org.junit.jupiter.params.provider.ValueSource;
   import static org.junit.jupiter.api.Assertions.*;

   class EvenNumberTest {
       @ParameterizedTest
       @ValueSource(ints = {2, 4, 6, 8, 10})
       void testIsEven(int number) {
           assertTrue(number % 2 == 0, number + " should be even");
       }
   }
   ```

   In this example:
   - @ParameterizedTest indicates that this is a parameterized test.
   - @ValueSource provides the test arguments.
   - The test will run five times, once for each value in the ValueSource.
   - This tests the "isEven" logic for multiple even numbers in a single, concise test method.

   This approach is more efficient and readable than writing five separate test methods or using a loop within a single test method. It clearly communicates the intent of testing multiple even numbers and makes it easy to add more test cases in the future.

