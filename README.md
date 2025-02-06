**## Underwater localization is achieved using three anchor nodes, with two designated as Anchor 1 and Anchor 2, and the third referred to as the mother node.
**# The MQTT protocol is implemented to synchronize the anchor nodes.
**# A method for converting coordinates from local to global frames has also been developed.******



Step 1: Connect Anchor 1 and Anchor 2 to the broker and wait for a command from the mother node.
Step 2: Connect the mother node to the broker and send the command.
Step 3: Prompt the user to input the global coordinates (latitude, longitude, altitude) for the origin, Anchor 1, and Anchor 2. (Ensure all altitudes are identical)
Step 4: Convert the global coordinates into a local frame, ensuring all z-values are near zero.
Step 5: Once the mother node sends the command, Anchor 1 and Anchor 2 acquire d1 and d2.
Step 6: After receiving d1 and d2 from Anchor 1 and Anchor 2, the mother node determines d3.
Step 7: Once d1, d2, and d3 are obtained, the mother node runs the optimizer.
Step 8: The optimizer returns the x and y coordinates of the unknown node, appends z = 0 to make it 3D.
Step 9: Convert the coordinates from local back to global. (Altitude remains the same as the anchor nodes)
Step 10: Request GPS sensor data for comparison. (The GPS sensor is deployed on the unknown node)
