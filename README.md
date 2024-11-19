<!-- hide -->
# Create a Multi-Language Translator in React using ChatGPT
<!-- endhide -->

<onlyfor saas="true" withBanner="true">
## 🌱 How to start this project?

Do not clone this repository because we are going to use a different template.

We recommend opening the `react template` using a provisioning tool like [Codespaces](https://4geeks.com/lesson/what-is-github-codespaces) (recommended) or [Gitpod](https://4geeks.com/lesson/how-to-use-gitpod). Alternatively, you can [clone the GitHub repository](https://4geeks.com/how-to/github-clone-repository) on your local computer using the `git clone` command.

This is the repository you need to open or clone:

```
https://github.com/4GeeksAcademy/react-hello
```

> ⚠ You will need to have Node.js installed if you do it locally, but all of that is already installed on Codespaces or Gitpod!
</onlyfor>

## 📝 Instructions

### Step 1: Set Up the Project

- [ ] Set up the boilerplate project from the provided React template.

- [ ] Follow the instructions in the README of the repository to set up your development environment.

### Step 2: Get Access to ChatGPT's API

- [ ] Sign up for an account at [OpenAI](https://www.openai.com/).

- [ ] Navigate to the API section and obtain your API key for accessing ChatGPT.

### Step 3: Create the Translation Form

- [ ] In your React app, create a form where users can input the text they want to translate.

- [ ] Add a dropdown or select input where users can choose the target language.

### Step 4: Connect to ChatGPT's API

- [ ] Use the user's input to create a prompt for the ChatGPT API to perform the translation.

- [ ] Make a request to the ChatGPT API when the form is submitted.

Example:

```jsx
  const handleTranslate = async ({ text, targetLanguage }) => {
    const prompt = `Translate the following text to ${targetLanguage}:\n\n"${text}"`;

    try {
      const response = await fetch('https://api.openai.com/v1/completions', {
        method: 'POST',
        headers: {
          'Authorization': `Bearer YOUR_OPENAI_API_KEY`,
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          model: 'text-davinci-003',
          prompt: prompt,
          max_tokens: 1000,
          temperature: 0,
        }),
      });

      const data = await response.json();
      const translation = data.choices[0].text.trim();
      setTranslatedText(translation);
    } catch (error) {
      console.error('Error translating text:', error);
    }
  };
```

> **Note:** Remember to replace `'YOUR_OPENAI_API_KEY'` with your actual OpenAI API key.

### Step 5: Display the Translated Text

- [ ] Display the translated text returned from the API to the user in your React app.

- [ ] Ensure the translation is presented in a readable format, possibly with styling to enhance user experience.

### Bonus Section

#### Additional Features to Practice and Improve the Project

1. **Source Language Selection:** Allow users to select the source language of the text.

2. **Language Detection:** Implement automatic language detection for the source text.

3. **Support Multiple Target Languages:** Add more language options for translation.

4. **History:** Keep a history of translations so users can revisit them.

5. **Error Handling:** Add robust error handling to manage API errors, network issues, or invalid inputs.

6. **Styling:** Enhance your app's appearance using CSS or styling libraries like [Bootstrap](https://getbootstrap.com/) or [Material-UI](https://material-ui.com/).

7. **Accessibility:** Ensure your app is accessible to all users, including those using screen readers.

Explore different enhancements to make your translator app more interactive and user-friendly!
