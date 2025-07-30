# Art Gallery BST Implementation

This implementation provides a robust foundation for managing an art gallery collection with efficient search and retrieval operations typical of BST-based systems.

## Overview

This Java program implements an Art Gallery management system using a Binary Search Tree (BST) to store and organize artwork pieces. The system allows for efficient addition, searching, and removal of artwork based on various criteria including creation year, cost, and name.

## Classes

### 1. Artwork Class
Represents an artwork piece with attributes:
- Name (including artist)
- Year of creation
- Cost

**Key Methods:**
- `compareTo()`: Compares artworks by year, then cost, then name
- `equals()`: Checks if two artworks are identical
- `toString()`: Returns formatted string representation

### 2. BSTNode Class
Generic binary search tree node implementation that holds data and references to left/right children.

### 3. ArtGallery Class
The main BST implementation for managing artwork with methods for:
- Adding/looking up artwork
- Finding the "best" (most expensive/recent) artwork
- Getting all artworks matching certain criteria
- Buying/removing artwork from the gallery

**Key Methods:**
- `addArtwork()`: Adds new artwork to the gallery
- `lookup()`: Checks if artwork exists
- `getBestArtwork()`: Returns most valuable artwork
- `buyArtwork()`: Removes artwork from gallery
- `toString()`: Returns sorted list of artworks

### 4. ArtGalleryTester Class
Comprehensive test suite verifying all functionality:
- Artwork comparison and equality
- BST operations (add, lookup, remove)
- Special queries (best artwork, lookup by criteria)
- Edge cases and error handling

## How to Use

1. Create an ArtGallery instance:
   ```java
   ArtGallery gallery = new ArtGallery();
   ```

2. Add artworks:
   ```java
   gallery.addArtwork(new Artwork("Starry Night, Van Gogh", 1889, 2000.0));
   ```

3. Search for artworks:
   ```java
   boolean exists = gallery.lookup("Mona Lisa, DaVinci", 1503, 1000.0);
   ```

4. Get the most valuable artwork:
   ```java
   Artwork best = gallery.getBestArtwork();
   ```

5. Remove artwork (when purchased):
   ```java
   gallery.buyArtwork("Guernica, Picasso", 1937, 3000.0);
   ```

## Testing

Run the test suite with:
```java
ArtGalleryTester.runAllTests();
```

Or run individual test methods to verify specific functionality.

## Key Features

- Efficient BST operations (O(log n) average case)
- Comprehensive error handling
- Flexible search capabilities
- Maintains artworks in sorted order
- Thread-safe operations (assuming proper synchronization)

## Limitations

- Not designed for concurrent access (would need synchronization for multi-threaded use)
- Artwork modifications after addition not supported (would break BST structure)
- Memory usage grows linearly with number of artworks
