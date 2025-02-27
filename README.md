# FP Front-End Challenge

In this task, you’ll build an MVP version of the new **PERMA** image feed in React Native, focusing on gesture-based interactions and displaying a feed of images with attributions.

![See Feed Design](./assets/feed-design.png)

You’ll work with **React Native Gesture Handler** to implement interactions. The **GestureHandlerRootView** provider is already in place in **_layout.tsx** so you don’t need to handle its configuration. 

Your work will be based in the **LatestFeed** component, which provides you with the following data:

- An unlimited query that hits our GraphQL endpoint, providing you with `feedItems`, which are of type `Photo`
- A list of `phrases` (max 25 chars), which can be used to choose a random image description for each image
- A list of `threads`, which are essentially a category applied to an image
- A list of `User` objects, which should be used to attribute the **_forward_** action to a random user

## Functional Specs

-  **For each image**:
    - Display the image
    - Display a `ForwardedBy` component with arrow, user attribution with avatar and username (see `PermaUserLockupFeed`), and thread (see `Tag`)
    - Show the description and photo attribution
- On **Tap + Hold**:
    - Fade out the ForwardedBy and photo description/attribution
    - Scale down the image
    - Add new recipients one by one at 250ms increments, showing the updated count at each interval and adding the user avatar around the image using the OrbitingCircle component
- On **Release**:
    - Scale the image back up + show the attributions
- On **Flick Up**:
    - Show the Forward component
- On **Flick Down**:
    - Show the Discard component

-  Optional - **Just for fun**:
    - Adapt the placement and sizing of the orbiting avatar images in `OrbitingCircle`

## Getting Started

1. **Clone** the repo:  
   ```bash
   git clone https://github.com/FUTUREPRIMITIVEXYZ/perma-frontend-challenge
   ```
2. **Grab environment variables** (reach out to the team for specifics)
3. **Install** the [Perma app](https://per.ma) from the iOS App Store
4. **Navigate** to the mobile directory and **install** dependencies:  
   ```bash
   cd mobile
   pnpm i
   ```
5. **Connect your iPhone** via USB
6. **Build for device**:  
   ```bash
   pnpm build-device
   ```
7. **Scan the QR code** to launch Perma on your device

## Additional Info

You might find the following info useful:

- **Theme Colors**: see `theme.ts` (`brand` object for brand colors)
- **Tailwind**: we use [`twrnc`](https://github.com/jaredh159/twrnc), invoked with `tw` and exported from `ThemeProvider`
- **Design System**: in `mobile/components/ui`
- **Icons**: in `mobile/icons/generated`
- **Storybook**: for viewing components in the UI library  
  ```bash
  pnpm storybook
  ```

  Explore the UI component library for references.

## Useful Components

We use composable components in places that make working with related data more convenient, eg:
- `NFT`
- `PermaUser`

Other components that may prove useful:
- `OrbitingCircle`
- `Typography`
- `NFTMediaViewer`
- `MediaViewer`
- `MediaViewerImage`
- `PermaUserLockupFeed`
- `Avatar`
- `Tag`
- `Forward`
- `Discard`

---

Feel free to reach out if you have questions or need clarification on any aspect of this challenge. Good luck!
