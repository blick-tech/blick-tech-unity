# BlickTech Unity Asset

This is the public repository for BlichTech Unity integration.

## Setup Guide

### Prerequisite

* You need to have a Blick Tech account. You can create it here: [https://panel.blick-tech.pl](https://panel.blick-tech.pl)
* You need to create a game in Blick Tech.

### Install asset

1. Download the latest release from GitHub Releases(https://github.com/bkostrowiecki/blick-unity/releases). The file is named `BlickTechUnity.unitypackage`
2. Drag and drop the file into your Unity Project.
3. Import all files.

### Configuring connection

#### Create Game Configuration

1. In `Project` window in `Assets` directory right-click on the view and select `Create -> Blick Tech -> Game Setup`.
2. Go to your game in [https://panel.blick-tech.pl](https://panel.blick-tech.pl)
3. Go to `Settings` tab
4. Click copy button beside the URL.
5. Paste it in property `URL` in your newly created `Game Setup Asset`.
6. Go to your game in [https://panel.blick-tech.pl](https://panel.blick-tech.pl) again
7. Go to `Settings` tab.
8. Click copy button beside the `Key`.
9. Paste it in property `Key` in your `Game Setup Asset`.

### Setup input tracking

#### Provide inputs

##### Old Input System

1. Go to your `Blick Tech Game Configuration`.
2. Select `Old Input System`.
3. If your game is City Builder, Deck Builder or Strategy Game, click `Apply Strategy Template` to apply default settings for those genres.
4. If your game is Action Game, First Person Shooter or Arcade, click `Apply Action Template` to apply default settings for those genres.

##### New Input System (Input Manager)

1. Go to your `Blick Tech Game Configuration`
2. Select `New Input System`
3. Drag & Drop your input asset to the `inputAsset` reference field.

### Setup play tracking

1. Go to your scene.
2. Right click on `Hierarchy` panel in the empty spot.
3. Select `Blick Tech -> Play`.
4. In `Inspector` panel in newly created game object in `Blick Tech Play (Script)` component click on dot on the right of `Settings` property.
5. Select your `Game Setup Asset` from list.
6. Click `Connect` to connect it to your game in `BlickTech`.
7. If proper game name appears in `Game Name` property, the game was successfully connected.
8. If game name does not show up, check if `URL` and `Key` matches data from your game's settings in [https://panel.blick-tech.pl](https://panel.blick-tech.pl)

By default, Blick Play will start gathering data when `OnEnable` is called and will stop on `OnDisable`.

### Setup objects tracking

It is required to have game object with `Blick Tech Play` component in the scene. To create it, see **Setup play tracking**.

#### Scene objects

1. Open your scene.
2. Select your game object in `Hierarchy` panel
3. Click `Add component` in the `Inspector` panel.
4. Select `Blick Tech Object` to add it to your game object.

#### Prefabs

1. Select your prefab in `Project` panel.
2. Click `Add component` in the `Inspector` panel.
3. Select `Blick Tech Object` to add it to your prefab.

#### Setup player's data tracking

It is required to have game object with `Blick Tech Play` or `Blick Tech Player` component in the scene. To create it, see **Setup play tracking** or **Setup only player's data tracking**.

1. Open your scene.
2. Select game object with player's information to `Hierarchy`.
3. Click `Add component` in the `Inspector` panel.
4. Select `Blick Tech Player Object` to add it to your game object.

### Setup only player's data tracking

You can setup only player's data tracking. It is useful if full player's data are present on other scene then your main gameplay. 

1. Go to your scene.
2. Right click on `Hierarchy` panel in the empty spot.
3. Select `Blick Tech -> Player`.
4. In `Inspector` panel in newly created game object in `Blick Tech Play (Script)` component click on dot on the right of `Settings` property.
5. Select your `Game Setup Asset` from list.

The data will be track from all objects with `Blick Tech Player Object`.

### Troubleshooting

#### Unity 6

The package is designed to be compatible with Unity from version 2022. It means that Unity may warn you about some deprecated code. You can allow it update it.

#### NewtonSoft related issues

The package has built-in NewtonSoft JSON package. If your project has one already installed, you can remove built-in version by deleting `Assets/BlickTech/Plugins/com.unity.nuget.newtonsoft-json@3.0.2`