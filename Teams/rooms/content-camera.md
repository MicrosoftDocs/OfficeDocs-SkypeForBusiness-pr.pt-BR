---
title: Saiba como configurar câmeras de conteúdo – Microsoft Teams
ms.author: serdars
author: serdarsoysal
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- seo-marvel-mar2020
description: Use uma câmera de conteúdo em uma Sala do Microsoft Teams, que interage com o software de processamento de imagens para permitir que os apresentadores desenhem em um quadro de whiteboard analógico.
ms.openlocfilehash: ced0a65c0c1fab25bd1b244aea7301d654c44a9e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508308"
---
# <a name="content-cameras"></a>Câmeras de conteúdo

Agora você pode usar uma câmera de conteúdo com um sistema de Sala do Microsoft Teams. Uma câmera de conteúdo interage com um software especial de processamento de imagens e um quadro de branco para permitir que um apresentador desenhista desenhista em um quadro de whiteboard analógico e compartilhe o conteúdo com participantes remotos.

Confira o vídeo a seguir para ver exemplos de funcionalidade de câmera de conteúdo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Configurar uma câmera de conteúdo

> [!NOTE]
> Sempre acate o código de construção de seu país ou área, o que pode definir uma distância mínima do chão ou um requisito de que o equipamento montado no teto seja protegido a um aparelho de teto ou outra estrutura. Siga as instruções de montagem do hardware fornecido com a câmera selecionada. Os kits de instalação da câmera OEM incluem uma câmera, ampliadores USB 2.0 e o cabeamento obrigatório.

O tamanho do quadro de branco usado para compartilhamento afeta o posicionamento da câmera. As recomendações de tamanho do quadro são:

- 3-6 ft. (0,9–1,8 m) de largura — Com suporte
- 6 a 9 pés de largura (1,8 a 2,7 m) de largura — recomendado
- 9 a 12 pés. (2,7 a 3,6 m de largura) — Com suporte
- Acima de 12 pés. (3,6 m) de largura — a câmera cobre de 9 a 12 pés. (2,7 a 3,6 m) e faz o resto.

## <a name="camera-location"></a>Local da câmera

O posicionamento ideal de uma câmera de conteúdo é centralizado verticalmente e horizontalmente no quadro de informações. Os códigos de construção locais podem ter restrições de altura que exigem que a câmera seja elevada acima da parte superior do quadro branco.

Você pode instalar a câmera de até 6 imagens. (152 mm) acima da parte superior do quadro de branco e centralizado no quadro branco, conforme mostrado. Certifique-se de que a imagem da câmera inclua pelo menos 6 imagens. (152 mm) de borda horizontal em ambos os lados. Você pode usar a visualização da câmera no aplicativo Salas do Microsoft Teams para determinar o posicionamento final da câmera.

![Diagrama de posicionamento da câmera de conteúdo](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Distâncias da câmera

Usando marcadores típicos do quadro de branco, a melhor experiência do usuário remoto é compartilhar traços de tinta no intervalo de 1 a 2 mm por pixel na imagem da câmera de conteúdo, e os melhores resultados usam 1,5 mm por pixel. Todas as câmeras com suporte fornecem resolução de 1920 x 1080, e algumas podem exceder essa resolução.

A distância da câmera do quadro de branco combina com a resolução da câmera e HFoV para determinar a distância do quadro de branco. A tabela a seguir mostra exemplos de distâncias para vários tamanhos de quadro de branco. Você pode usar esses valores como pontos de partida para determinar o posicionamento final da câmera de conteúdo.

**Distância da câmera do quadro de branco**

| HFoV da câmera |3 pés. (0,91 m)     | 6 pés. (1,8 m)    | 9 pés. (2,74 m)        |12 pés.  (3,65 m)         | Distância máxima do Whiteboard  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80°         | 1,79 m. (0,54 m) | 3,58 m. (1,09 m)  | 5,36 m. (1,6 m)    |7,15 m. (2,17 m) |7,51 m. (2,28 m) |
| 90°         | 1,5 pé. (0,45 m) | 3,00 m. (0,91 m)   | 4,5 m. (1,37 m)    |6,0 m. (1,82 m)    |6,3 m. (1,92 m) |
| 100°        | 1,26 m. (0,38 m)| 2,52 m. (0,77 m)   | 3,78 m. (1,15 m)   |5,03 m. (1,53 m)   |5,29 m. (1,61 m) |
| 110°        | 1,05 m. (0,32 m)| 2,10 m. (0,64 m)   | 3,15 m. (0,96 m)   |4,2 m. (1,28 m)    |4,41 m. (1,31 m) |
| 120°        | 0,87 m. (0,26 m)| 1,73 m. (0,52 m)   | 2,60 m. (0,79 m)   |3,46 m. (1,05 m)   |3,64 m. (1,10 m) |
|             |               |                  |                  |        |                    |                  |

A distância entre a câmera de conteúdo e a parede na qual o quadro de branco é montado depende do HFoV desse modelo de câmera, que varia. Instale câmeras com um HFoV maior (120 graus por exemplo) mais próximo da parede e câmeras com um HFoV mais estreito mais longe da parede. Verifique o HFoV antes de começar a instalar a câmera escolhida.

Se você tiver whiteboards com mais de 12 pés. (3,65 m) ou sem cantos (como whiteboards de parede completos), você pode colocar a câmera em qualquer lugar no meio. O software de aprimoramento seleciona uma área no meio se ele não encontrar cantos do quadro de branco.

> [!NOTE]
> Você pode usar fita de cor escura ou outros itens para criar uma área de câmera de conteúdo definida em um quadro branco de parede cheia.
>
> Você pode optar por ter a câmera em um tripé movêvel em vez de uma montagem permanente. Coloque o tripé centralizado no quadro de branco. Essa configuração pode ser temporária ou usada quando há pouca chance de bater sobre o equipamento. Se você usar uma montagem temporária, lembre-se de que o aprimoramento do conteúdo será afetado se você mover a câmera após o compartilhamento inicial e você precisará compartilhar de novo para corrigir o movimento.
>
> Não há suporte para um quadro de texto que não seja branco.

## <a name="supported-cameras"></a>Câmeras com suporte

Para determinar se você pode usar uma câmera como uma câmera de conteúdo, confira as versões de firmware certificadas para periféricos de áudio e [vídeo USB.](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals)

Ou consulte o marketplace de dispositivos microsoft teams para kits de câmera de conteúdo compatíveis no [aka.ms/teamsdevices.](https://aka.ms/teamsdevices)

## <a name="camera-settings"></a>Configurações da câmera

Depois que a câmera estiver instalada na sala, desarmá-la no console salas do Microsoft Teams dessa sala:

1. Selecione **o ícone Configurações** ![ de Configurações, entre como Administrador e selecione ](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) **Configurações do Dispositivo.**
2. Na seção **Padrões da Câmera,** selecione a câmera de conteúdo e certifique-se de que a **opção Aprimoramentos de** Conteúdo está selecionada.
3. (Opcional) Se a câmera foi instalada de cabeça para baixo porque a câmera foi instalada do teto, verifique a opção Girar a câmera de conteúdo **180°.**
4. Selecione **Salvar e sair.**

![Configuração da câmera de conteúdo](../media/content-camera.png)

Você também pode ajustar essas configurações remotamente usando um [arquivo de configuração XML.](xml-config-file.md)

## <a name="see-also"></a>Confira também

[Gerenciar remotamente as configurações de console de salas do Microsoft Teams com um arquivo de configuração XML](xml-config-file.md)

[Requisitos das Salas Microsoft Teams](requirements.md)


