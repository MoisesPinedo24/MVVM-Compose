MVVM Login Project with Jetpack Compose
This is a personal project built to demonstrate my knowledge of MVVM architecture and Jetpack Compose in Android development.
It implements a simple login screen that validates user input (email & password), enables/disables the login button, and shows a loading indicator.


Code Structure
 1. MainActivity (View - entry point)
Sets up the theme (MVVMLoiginTheme).
Creates the main Surface.
Calls LoginScreen and injects an instance of LoginViewModel.
Its only responsibility is to connect the UI with the ViewModel.


2. LoginViewModel (ViewModel - business logic)
Manages state with LiveData:
email, password → hold user input.
loginEnable → enables button only if inputs are valid.
isLoading → controls the loading indicator.
Key methods:
onLoginChanged(email, password) → validates input and updates state.
onLoginSelected() → simulates a login process using delay.

3. LoginScreen (View - UI with Compose)
Observes LiveData values from the ViewModel using observeAsState.
Renders UI based on state:
isLoading = true → shows CircularProgressIndicator.
isLoading = false → shows inputs and login button.
Main components:
EmailField & PasswordField → text inputs with custom styles.
LoginButton → enabled/disabled based on loginEnable.
ForgotPassword → clickable link.
HeaderImage → decorative image at the top.





How it works
The user types email and password.
The View calls onLoginChanged() in the ViewModel.
The ViewModel validates inputs and updates loginEnable.
When login button is clicked, onLoginSelected() sets isLoading to true.
The UI reacts and shows a CircularProgressIndicator.
After 4 seconds, loading stops and the UI resets.



About this project
This is my own project, created with the goal of showcasing my skills in Android development using MVVM and Jetpack Compose.
It is not just a sample, but a practical demonstration of how I structure code and handle reactive UI updates.
