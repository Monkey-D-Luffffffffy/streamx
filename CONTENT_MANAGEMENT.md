# StreamX Content Management Guide

## Easy Content Management

All your content is managed through a single, easy-to-edit file: `server/content-data.ts`

This file contains all your movies and TV shows in a simple JavaScript array. No admin interface needed - just edit the file directly!

## Adding New Content

1. Open `server/content-data.ts`
2. Copy one of the existing entries
3. Change the details to match your new content
4. Save the file and the changes will appear immediately

### Example:
```javascript
{
  id: "7", // Make this unique!
  title: "Your New Movie",
  description: "A great description of your movie...",
  year: 2024,
  duration: "2h 15m", // For movies: "2h 15m", for TV: "10 Episodes"
  genre: "Action", // Action, Drama, Comedy, Thriller, Sci-Fi, Romance, Documentary
  type: "movie", // "movie" or "tv"
  category: "trending", // "trending", "popular", or "original"
  rating: "HD", // "HD" or "4K" (video quality)
  thumbnailUrl: "https://your-image-url.com/thumbnail.jpg",
  googleDriveUrl: "https://drive.google.com/file/d/YOUR_FILE_ID/preview",
  isOriginal: 0 // 1 for StreamX Originals, 0 for regular content
}
```

## Field Explanations

- **id**: Must be unique for each item (use numbers or strings)
- **title**: The name of your movie/show
- **description**: Brief plot summary
- **year**: Release year
- **duration**: 
  - Movies: "2h 15m" format
  - TV Shows: "8 Episodes" or "Season 1"
- **genre**: Choose from Action, Drama, Comedy, Thriller, Sci-Fi, Romance, Documentary, etc.
- **type**: Either "movie" or "tv"
- **category**: 
  - "trending" - Shows on homepage trending section
  - "popular" - Shows in popular/movies section
  - "original" - StreamX original content
- **rating**: "HD" or "4K" (refers to video quality)
- **thumbnailUrl**: Link to cover image (recommended 800x450 pixels)
- **googleDriveUrl**: Your Google Drive video link in format: `https://drive.google.com/file/d/FILE_ID/preview`
- **isOriginal**: Set to 1 for StreamX originals, 0 for regular content

## Getting Google Drive Video URLs

1. Upload your video to Google Drive
2. Right-click the video → "Get link"
3. Make sure it's set to "Anyone with the link can view"
4. Copy the link - it will look like: `https://drive.google.com/file/d/1ABC123XYZ456/view`
5. Change `/view` to `/preview` at the end
6. Final URL: `https://drive.google.com/file/d/1ABC123XYZ456/preview`

## Getting Good Thumbnail Images

For best results, use images that:
- Are 800x450 pixels (16:9 aspect ratio)
- Are high quality movie posters or stills
- Work well with dark themes
- Load quickly

Good sources:
- Unsplash.com (free stock photos)
- TMDB (for movie posters, if allowed)
- Your own custom artwork

## Categories Explained

- **Trending**: Featured content on the homepage hero section
- **Popular**: Regular movies and popular content
- **Original**: StreamX exclusive content (will show the "StreamX Original" badge)

## Making Changes Live

1. Edit `server/content-data.ts`
2. Save the file
3. The app will automatically reload with your changes
4. No restart needed!

## Common Issues

### Video Won't Play
- Make sure the Google Drive link ends with `/preview`
- Check that the file is shared publicly ("Anyone with the link can view")
- Verify the file ID is correct

### Thumbnail Won't Load
- Make sure the image URL is accessible publicly
- Try opening the image URL in a new browser tab to test
- Use HTTPS URLs when possible

### Content Not Appearing
- Check that the `id` is unique
- Make sure all required fields are filled out
- Verify the JSON syntax is correct (commas, quotes, etc.)

## Backup Your Content

Since all content is in `server/content-data.ts`, you can easily:
- Copy the file to backup your content
- Version control it with git
- Share it between projects
- Edit it in any text editor

This makes content management much simpler than using a database or admin interface!