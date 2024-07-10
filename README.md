
# Create an image with white background
width, height = 800, 1200
image = Image.new('RGB', (width, height), 'white')
draw = ImageDraw.Draw(image)

# Load a font
try:
    # Try to use a default font
    font_title = ImageFont.truetype("arial.ttf", 60)
    font_subtitle = ImageFont.truetype("arial.ttf", 40)
    font_text = ImageFont.truetype("arial.ttf", 30)
except IOError:
    # Fallback to default PIL font
    font_title = ImageFont.load_default()
    font_subtitle = ImageFont.load_default()
    font_text = ImageFont.load_default()

# Title
title = "Challenge Commercial"
subtitle = "Destination Disneyland !"
draw.text((width//2 - draw.textlength(title, font=font_title)//2, 50), title, fill="black", font=font_title)
draw.text((width//2 - draw.textlength(subtitle, font=font_subtitle)//2, 150), subtitle, fill="black", font=font_subtitle)

# Main text
main_text = (
    "Chers commerciaux,\n\n"
    "Vous êtes prêts à relever un nouveau défi et à démontrer vos talents de vente ? "
    "Nous lançons un challenge excitant qui pourrait vous mener à la magie de Disneyland !\n\n"
    "Comment participer ?\n"
    "Objectif : Réaliser le plus grand nombre de ventes et générer le chiffre d'affaires le plus élevé.\n"
    "Période : Du 1er août au 31 août 2024.\n\n"
    "À gagner !\n"
    "Le commercial qui se distinguera par ses performances se verra offrir une journée inoubliable "
    "à Disneyland avec la possibilité de prendre un partenaire de son choix !\n\n"
    "Critères de sélection :\n"
    "1. Nombre total de ventes réalisées.\n"
    "2. Chiffre d'affaires généré.\n\n"
    "Règles :\n"
    "Seules les ventes enregistrées durant la période du challenge seront comptabilisées.\n"
    "Les résultats seront vérifiés et validés par notre service financier.\n\n"
    "Annonce du gagnant :\n"
    "Le grand gagnant sera annoncé lors de notre réunion mensuelle en septembre.\n\n"
    "Bonne chance à tous ! Que la magie de Disneyland vous motive à atteindre des sommets !\n\n"
    "Pour toute question ou information complémentaire, contactez le service des ressources humaines.\n\n"
    "[Votre Entreprise]\n"
    "L'équipe de direction"
)

# Draw the main text
draw.multiline_text((50, 250), main_text, fill="black", font=font_text, spacing=10)

# Save the image
image_path = "/mnt/data/challenge_flyer_no_emojis.png"
image.save(image_path)
image_path
``` &#8203;:citation[oaicite:0]{index=0}&#8203;
