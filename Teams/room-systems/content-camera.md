---
title: Gerenciar as configurações de um console de salas do Microsoft Teams remotamente com um arquivo de configuração XML
ms.author: kenwith
author: kenwith
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: Este artigo discute o gerenciamento remoto das configurações padrão usadas por um dispositivo de salas do Microsoft Teams, incluindo a aplicação de um tema personalizado.
ms.openlocfilehash: 35ca0898dbaa1309848f4725f21cd11bf9511752
ms.sourcegitcommit: 74c06b00ff78dc816a59e6c59e9be87181fc0f3e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2019
ms.locfileid: "39669250"
---
# <a name="content-cameras"></a>Câmeras de conteúdo

Agora você pode usar uma câmera de conteúdo com um sistema de sala do Microsoft Teams. Uma câmera de conteúdo interage com um software de processamento de imagens especial e um quadro de comunicações para permitir que um apresentador desenhe em um quadro de comunicações analógico e compartilhe o conteúdo com participantes remotos.

Consulte o vídeo a seguir para obter exemplos de funcionalidade de câmera de conteúdo.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3E7fy]

## <a name="set-up-a-content-camera"></a>Configurar uma câmera de conteúdo

> [!NOTE]
> Sempre respeite o código de construção do seu país ou da área, o que pode definir uma distância mínima do andar ou um requisito de que o equipamento montado pelo teto seja protegido a um Rafter ou a outra estrutura. Siga a instrução de montagem para o hardware fornecido com a câmera que você selecionou. Os kits de montagem de câmera OEM incluem uma câmera, extensores USB 2,0 e cabeamento obrigatório.

O tamanho do quadro de comunicações usado para compartilhamento afeta o posicionamento da câmera. As recomendações de tamanho de quadro são:

- de 3 a 6 pés (0,9 a 1,8 m) de largura — compatível
- de 6 a 9 pés (1,8 a 2.7 m) de largura — recomendado
- de 9 a 12 pés (2,7 a 3,6 m), com suporte
- Acima de 12 pés (3,6 m) de largura, a câmera cobre de 9 a 12 pés (2.7 – 3,6 m) e corta o restante.

## <a name="camera-location"></a>Local da câmera

O posicionamento ideal de uma câmera de conteúdo é centralizado verticalmente e horizontalmente no quadro de comunicações. Os códigos de construção locais podem ter restrições de altura que exigem que a câmera seja elevada e elevada do que o topo do quadro branco.

Você pode instalar a câmera até 6. (152 mm) maior do que o topo do quadro de comunicações e centralizado no quadro branco, conforme mostrado. Verifique se a imagem da câmera inclui pelo menos um 6 in. (152 mm) borda em ambos os lados horizontalmente. Você pode usar a visualização da câmera no aplicativo salas do Microsoft Teams para determinar o posicionamento final da câmera.

![Diagrama de posicionamento de câmera de conteúdo](../media/Magic-whiteboard.png)

### <a name="camera-distances"></a>Distâncias da câmera

Usando marcadores típicos do quadro de comunicações, a experiência do usuário remoto ideal é compartilhar traços de tinta no intervalo de 1 a 2 mm por pixel na imagem da câmera de conteúdo, e os melhores resultados usam 1,5 mm por pixel. Todas as câmeras compatíveis fornecem a resolução de 1920 x 1080 e alguns podem exceder essa resolução.

A distância da câmera do whiteboard combina-se com a resolução da câmera e HFoV para determinar a distância do quadro de comunicações. A tabela a seguir mostra exemplos de distâncias para vários tamanhos de quadro de comunicações. Você pode usar esses valores como ponto de partida para determinar o posicionamento final da câmera de conteúdo.

**Distância da câmera do quadro de comunicações**

| Câmera HFoV |3 pés (0,91 m)     | 6 pés (1,8 m)    | 9 pés (2,74 m)        |12 pés.  (3,65 m)         | Distância máxima do quadro de comunicações  |
|:---         |:---               |:---                |:---                 |:---             | :--- |
| 80 °         | 1,79 pés (0,54 m) | 3,58 pés (1, 9 m)  | 5,36 pés (1,6 m)    |7,15 pés (2,17 m) |7,51 pés (2,28 m) |
| 90 °         | 1,5 pés (0,45 m) | 3, 0 pés (0,91 m)   | 4,5 pés (1,37 m)    |6,0 pés (1,82 m)    |6,3 pés (1,92 m) |
| 100 °        | 1,26 pés (0,38 m)| 2,52 pés (0,77 m)   | 3,78 pés (1,15 m)   |5, 3 pés (1,53 m)   |5,29 pés (1,61 m) |
| 110 °        | 1, 5 pés (0,32 m)| 2,10 pés (0,64 m)   | 3,15 pés (0,96 m)   |4,2 pés (1,28 m)    |4,41 pés (1,31 m) |
| 120 °        | 0,87 pés (0,26 m)| 1,73 pés (0,52 m)   | 2,60 pés (0,79 m)   |3,46 pés (1, 5 m)   |3,64 pés (1,10 m) |
|             |               |                  |                  |        |                    |                  |

A distância entre a câmera de conteúdo e a parede em que o whiteboard é montado depende da HFoV para esse modelo de câmera, o que varia. Instale câmeras com uma HFoV maior (120 graus), por exemplo, mais perto da parede, e câmeras com HFoV mais estreita e longe da parede. Verifique o HFoV antes de começar a instalar a câmera escolhida.

Se você tiver quadros de comunicações maiores do que 12 pés (3,65 m) ou sem cantos (como quadros de comunicações em parede cheia), poderá colocar a câmera em qualquer lugar do meio. O software de aprimoramento seleciona uma área no meio se não conseguir encontrar os cantos do quadro de comunicações.

> [!NOTE]
> Você pode usar uma fita colorida escura ou outros itens para criar uma área de câmera de conteúdo definida em um quadro branco de parede cheia.
>
> Você pode optar por fazer com que a câmera seja montada em um tripé móvel, em vez de uma montagem permanente. Coloque o tripé centralizado no quadro de comunicações. Esta configuração pode ser temporária ou usada onde há pouca chance de vazar sobre o equipamento. Se você usar uma montagem temporária, lembre-se de que a melhoria do conteúdo será afetada se você mover a câmera após o compartilhamento inicial e será necessário compartilhar novamente para corrigir o movimento.
>
> Não há suporte para um quadro de escrita que não está em branco.

## <a name="supported-cameras"></a>Câmeras com suporte

Para determinar se você pode usar uma câmera como uma câmera de conteúdo, consulte [versões de firmware certificado para periféricos de áudio e vídeo USB](requirements.md#certified-firmware-versions-for-usb-audio-and-video-peripherals).

Ou, consulte o Marketplace de dispositivos do Microsoft Teams para kits de câmera de conteúdo suportados em [aka.ms/teamsdevices](https://aka.ms/teamsdevices).

## <a name="camera-settings"></a>Configurações da câmera

Depois que a câmera estiver instalada na sala, configure-a no console de salas do Microsoft Teams da sala:

1. Selecione **** ![o ícone](../media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)configurações de configurações, faça logon como administrador e selecione **configurações de dispositivo**.
2. Na seção **padrões da câmera** , selecione a câmera de conteúdo e certifique-se de que a opção **aprimoramentos de conteúdo** esteja selecionada.
3. Adicionais Se a câmera foi instalada de cabeça para baixo porque a câmera foi montada a partir do teto, marque a opção **girar conteúdo câmera 180 °** .
4. Selecione **salvar e sair**.

![Configuração da câmera de conteúdo](../media/content-camera.png)

Você também pode ajustar essas configurações remotamente usando um [arquivo de configuração XML](xml-config-file.md).

## <a name="see-also"></a>Confira também

[Gerenciar as configurações de um console de salas do Microsoft Teams remotamente com um arquivo de configuração XML](xml-config-file.md)

[Requisitos de salas do Microsoft Teams](requirements.md)

> [!NOTE]
> Certos dispositivos da sala do Microsoft Teams que têm consoles baseados em Microsoft Surface pro (como o Logitech Smartdock e Crestron SR) ainda não dão suporte à câmera de conteúdo. O suporte para esses dispositivos será adicionado mais tarde no CY2019. 
>
