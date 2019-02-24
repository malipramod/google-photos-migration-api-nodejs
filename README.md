# Google Photos Migration API - NodeJS

Google Photos Migration API Developed in NodeJS. It uses Express framework for API design.

## Architecture Overview

It uses route.js as main routing file. Routes/controller/migrate-controller.js is main controller being called from route  *POST: {baseURL}migrateAlbum*.

```JavaScript
/**
     * Uploads Media Item from one Account to another
     * @param {string} authToken
     * @param {array} mediaItems
     * @param {string} albumData
     */
    MigrateAlbum(authToken, mediaItems, albumData);
```

## Migrate Controller flow and Google Photos API being used

1. Creates a new Album in destination Google Photos Account
    It uses *Create Album API* by Google Photos
2. Uploads media items and gets Upload Token
    It uses Google Photos' *Upload API* which returns *Upload Tokens*
3. Using Upload Tokens generate in Step 2, upload it to Google Photos account
    It uses *mediaItems:batchCreate API* to upload media

## How to use

How to Use <https://github.com/malipramod/google-photos-migration-node_module/blob/master/demo/migrate-demo.js>

## Deployed at

<https://google-photos-migration.herokuapp.com>