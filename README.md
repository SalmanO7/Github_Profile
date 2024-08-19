# GitHub Profile Search

This project is a web application that allows users to search for GitHub profiles by username. It fetches and displays information such as the user's avatar, name, bio, follower count, following count, and the number of public repositories using the GitHub API.

## Features

- **Search by Username:** Input a GitHub username to fetch and display the profile details.
- **Responsive Design:** The application is fully responsive, ensuring a good user experience on both desktop and mobile devices.
- **Profile Information Display:** Displays key information about the user including avatar, name, bio, followers, following, and repository count.
- **GitHub API Integration:** Utilizes the GitHub API to retrieve real-time data for any GitHub user.

## Technologies Used

- **HTML**
- **CSS**
- **JavaScript**
- **GitHub API**

## API Usage

This project uses the [GitHub REST API](https://docs.github.com/en/rest) to retrieve user profile information. When a username is entered and the search button is clicked, an API call is made to `https://api.github.com/users/{username}`, where `{username}` is the name of the GitHub user being searched.

### Example API Request Using `try-catch`

```javascript
async function fetchGitHubProfile(username) {
    try {
        const response = await fetch(`https://api.github.com/users/${username}`);
        if (!response.ok) {
            throw new Error(`User not found: ${response.statusText}`);
        }
        const data = await response.json();
        console.log(data);
        // Display the data on the page
    } catch (error) {
        console.error('Error fetching the GitHub profile:', error);
        // Handle the error (e.g., show an error message on the page)
    }
}
