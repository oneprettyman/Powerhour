# Powerhour
Powerhour build
const powerhourLength = 60; // Set the number of minutes for the powerhour

const songs = [
    "https://www.youtube.com/watch?v=dQw4w9WgXcQ",
    "https://www.youtube.com/watch?v=JGwWNGJdvx8",
];

// Shuffle the songs
songs.sort(() => Math.random() - 0.5);

const startTime = Date.now();
const endTime = startTime + powerhourLength * 60 * 1000;

// Loop through the songs, playing one song per minute
for (const song of songs) {
    // Play the video
    window.open(song);

    // Wait until the next minute before playing the next song
    const currentTime = Date.now();
    const waitTime = endTime - currentTime;
    if (waitTime > 0) {
        await new Promise((resolve) => setTimeout(resolve, waitTime));
    }
}

// Display a message at the end of the powerhour
console.log("Congratulations, you've completed the powerhour challenge!");
