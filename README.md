# Craft to Exile 2 Minecraft Server

This repository contains the Docker configuration for a Craft to Exile 2 modded Minecraft server.

## For Players

### Installing Minecraft (using SKLauncher)
1. Download and Install SKLauncher
    - Visit [SKLauncher's official website](https://skmedix.pl/downloads)
    - Download the installer for your operating system
    - Run the installer and follow the setup wizard

2. Account Setup
    - Launch SKLauncher
    - Create a new account or sign in to existing one
    - Select "Java Edition" as your game version

3. Customize Your Profile (Optional)
    - Click the "My Account" icon in the top-right
    - Navigate to "Customization"
    - Personalize your experience:
      * Set your preferred username
      * Upload or choose a custom skin
      * Apply a cape if available
    - Click "Save" to apply changes

### Installing Craft to Exile 2
1. Download Craft to Exile 2 (Version 2-0.9.2)
    - Go to [CurseForge - Craft to Exile 2](https://www.curseforge.com/minecraft/modpacks/craft-to-exile-2/files/6161978)
    - Click the "Download" button
    - Save the ZIP file to a location you can easily find

2. Install the Modpack in SKLauncher
    - Open SKLauncher
    - Click "Installations Manager" in the top-left
    - Select "Import Modpack"
    - Browse to your downloaded ZIP file
    - Click "Open" to start installation

3. Wait for Installation
    - SKLauncher will download and install all required mods
    - This may take several minutes depending on your internet speed
    - Don't close SKLauncher during installation

4. Launch the Game
    - Once installation completes, the new Craft to Exile 2 instance will appear
    - Select it from your instance list
    - Click "Play" to start the game

### Joining the Server
1. Get the current server URL from the Playit service
    - Note: The server URL may change periodically if using the free Playit service
2. In Minecraft, go to Multiplayer
3. Click "Add Server"
4. Paste the Playit URL
5. Click "Done" and join the server

### Recommended Settings
- Allocate at least 4GB RAM to your Minecraft client, recommended is 8GB

## For Server Operators

### Server Requirements
- Docker Engine installed
- Docker Compose installed
- At least 4GB RAM available
- Stable internet connection
- [Playit.gg Agent](https://github.com/playit-cloud/playit-agent) configured for port forwarding
- CurseForge API key ([How to obtain](https://support.curseforge.com/en/support/solutions/articles/9000208346-about-the-curseforge-api-and-how-to-apply-for-a-key))

### Starting the Server
1. Clone this repository
2. Create `.env` file from the example:
    ```bash
    cp .env.example .env
    ```
    Then edit `.env` with your API keys.
3. Start the server using Docker Compose:
    ```bash
    docker-compose up -d
    ```
4. Wait for Playit.gg to initialize automatically
    - The agent will configure port forwarding for Minecraft (25565)
    - The Playit URL will be shown in the logs
5. Monitor logs with:
    ```bash
    docker-compose logs -f
    ```
6. Server will be ready when you see "Done!" in the console logs

### Server Management
- Server data persists in Docker volumes
- Configuration files are mounted from the `config` directory
- To stop the server:
```bash
docker-compose down
```
- To restart the server:
```bash
docker-compose restart
```

### Common Issues
- If container fails to start, check Docker logs
- Ensure Docker has enough resources allocated
- For permission issues, check Docker volume permissions
- Make sure all mods are properly synchronized with the server version
