from PIL import Image, ImageDraw, ImageFont

def create_necklace_image():
    bee_design = [
        "  ,--./,-.  ",
        " / #      \\ ",
        "|          |",
        " \\.-'-,-'/ ",
        "  `V_/V_'  "
    ]

    # Set the image size based on the ASCII art dimensions
    width, height = len(bee_design[0]), len(bee_design)

    # Create a new image with a white background
    image = Image.new("RGB", (width, height), "white")
    draw = ImageDraw.Draw(image)

    # Use a monospaced font to preserve the ASCII art spacing
    font = ImageFont.truetype("path/to/your/font.ttf", size=12)

    # Draw the ASCII art on the image
    for y, line in enumerate(bee_design):
        draw.text((0, y*12), line, fill="black", font=font)

    # Save the image
    image.save("necklace_design.png")

# Call the function to create the necklace image
create_necklace_image()
