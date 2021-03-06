# Beat Saber Local Leaderboards

View leaderboards for Beat Saber.

## Usage:

### React App
The app itself is not functional but is under rapid development. See progress with:

```
npm start
```

### Storybook
Storybook is being used to develop components in isolation. View current components with:

```
npm run storybook
```

## Code Structure

### index.tsx
This serves as a thin wrapper around the main application, providing it with environment related information such as environment variables, data providers, etc. For example, test or development environments may use different providers, endpoints, etc. which should be passed in to the application via `index.tsx`.

### app.tsx
The entry point to the main application. It receives external configuration information as props and uses that to power the actual application.

### src/pages/
These are the "application level" components. They should not introduce new UI components but should instead provide data and coordination for existing components.

### src/components/
These are entirely presentational and should be able to be replaced with a component that takes the same data without affecting the behavior of the application. These components should also be able to be copied and used in an unrelated react application without much effort, if any. Ideally all new components here should have a corresponding entry in `stories/` demonstrating their use and appearance.

### stories/
This directory contains "stories" which demonstrate uses and appearance for different components. Related components should be added to the same story.

## Backlog

### UI
* [X] Create "Song list" stories
* [X] Create "Songs Page" story
* [X] Add "Songs Page" to app.tsx using static data
* [ ] Create "Song Page" stories
* [ ] Navigate to "Song page" when clicking song title in song list
* [ ] Create "User Page" stories
* [ ] Navigate to "User Page" when clicking user name in song list or song page
* [ ] Navigate to "Song Page" when clicking song name in User Page
* [ ] Alternate between "Daily" and "All time" leaderboard
* [ ] Search / Filter

### Backend
* [ ] Provide endpoint for getting data
* [ ] Push data to backend whenever leaderboard files change

## Acknowledgements
This project was bootstrapped with [Create React App](https://github.com/facebookincubator/create-react-app).