import pygame
import os


#Initialisation de Pygame :


pygame.init()


#Configuration de la fenêtre :
largeur, hauteur = 400, 300
fenetre = pygame.display.set_mode((largeur, hauteur))
pygame.display.set_caption("Sound")

#Chargement des Sons :
sons = {
    "son1": pygame.mixer.Sound("./sound_api/ASMR.mp3"),
    "son2": pygame.mixer.Sound("./sound_api/Aznavour & Zemmour.mp3"),
    
}

#Configuration des Boutons :
boutons = {
    "Bouton1": {"son": "son1", "rect": pygame.Rect(50, 50, 100, 50)},
    "Bouton2": {"son": "son2", "rect": pygame.Rect(200, 50, 100, 50)},
    
}

#Rendu Graphique dans la Fenêtre :
en_cours = True
while en_cours:
    for evenement in pygame.event.get():
        if evenement.type == pygame.QUIT:
            en_cours = False
        elif evenement.type == pygame.MOUSEBUTTONDOWN:
            for bouton, info in boutons.items():
                if info["rect"].collidepoint(evenement.pos):
                    sons[info["son"]].play()

    #Actualisation de l'Affichage :
    fenetre.fill((255, 255, 255))
    for bouton, info in boutons.items():
        pygame.draw.rect(fenetre, (0, 128, 255), info["rect"])
        font = pygame.font.Font(None, 36)
        texte = font.render(bouton, True, (255, 255, 255))
        fenetre.blit(texte, (info["rect"].x + 10, info["rect"].y + 10))

    pygame.display.flip()

#Arrêt de Pygame :
pygame.quit()
