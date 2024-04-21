# 3D Hex Tile System for Godot
3D Hex Tile System for Godot, basic implementation of tile laying in Carcassone/Dorfromantik.
Based on [https://www.redblobgames.com/grids/hexagons/](https://www.redblobgames.com/grids/hexagons).

Was meant to be used for the initial Godot version of [Solo Train Game](https://github.com/AriJalk/SoloTrainGameUnity/) and was extracted from it.

## Features
Adding or removing tiles from the world, including ability to undo every action.
Uses a Freeform map dynamic map meaning islands of seperated hexes could be created without needing to store empty ones.

## Usage
* The Hex class is data representation of a hex and uses Cube Coordinates and is the basis for the system.
Initialized with QRS coordinates.

* The HexGrid class provides static functions to handle most hex logic and transformations.
Main usage is through 
static func hex_to_world(hex : Hex, hex_size: float, gap_proportion: float, orientation : Orientation = Layout.layout_flat) -> Vector3

* The TileManager class is the Game oriented side of the system, abstracting the creation and positioning of the actual 3D HexTile nodes.
Also used for storing the map using a dictionary.
Each possible position has a slot which may contain a tile.
Main usage is through:
func add_tile(hex_data : Hex) -> HexTile [Adds a hex to the map if possible with the specified hex coordinates)
func remove_tile(hex : Hex) -> void [Removes a hex if it exists]
func add_slot(hex_data: Hex) -> HexSlot [ 
func get_slot(hex) -> HexSlot [Get the world slot of a possible tile]


![Demonstration](HexGrid.gif)</br>