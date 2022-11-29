---
title: Requisitos de hardware para o Microsoft Teams
ms.reviewer: microthk, sthurlow
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.localizationpriority: high
search.appverid: MET150
description: Neste artigo, você aprenderá sobre os requisitos de hardware necessários para instalar e executar o Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3de0ed17ceee33106e3281707d90427569558922
ms.sourcegitcommit: 75b29de261b4de652c7f2e89da4ad7158da773f1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/29/2022
ms.locfileid: "69183010"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Requisitos de hardware para o Microsoft Teams

Todos os requisitos das seções a seguir se aplicam aos aplicativos da área de trabalho do Microsoft Teams e do aplicativo Web da equipe.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Requisitos de hardware para o Teams em um computador Windows

| Componente | Requisito |
|---------|---------|
|Computador e processador    | Mínimo de 1,1 GHz ou mais rápido, dois núcleos<br><br>Observação: para processadores Intel, deve ser considerada a velocidade máxima atingida usando a tecnologia Intel Note Plus (Max Note Frequency)         |
|Memória     |  4,0 GB de RAM |
|Disco rígido    | 3 GB de espaço em disco disponível        |
|Display    |   Resolução de tela 1024 x 768 |
|Hardware gráfico |  Sistema Operacional Windows: a aceleração de hardware de elementos gráficos requer o DirectX 9 ou posterior, com o WDDM 2.0 ou superior para Windows 10 (ou WDDM 1.3 ou superior para Windows 10 Fall Creators Update)
|Sistema operacional  |    Windows 11, Windows 10 (exceto Windows 10 LTSC para aplicativo da área de trabalho do Teams), Windows 10 no ARM, Windows 8.1, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2. Observação: Recomendamos usar a versão mais recente do Windows e os patches de segurança disponíveis.|
|Versão do .NET    |  Exige .NET 4.5 CLR ou posterior       |
|Vídeo    |  Câmera de vídeo USB 2.0       |
|Dispositivos    |   Câmera de notebook, microfone e alto-falantes padrão    |
|Chamadas de vídeo e reuniões|<ul><li>Requer processador de dois núcleos. Para maior resolução de compartilhamento de vídeo/tela e taxa de quadros, um processador de quatro núcleos ou melhor é recomendado.</li> <li>Os efeitos de vídeo em tela de fundo exigem o Windows 10 ou um processador com o conjunto de instruções AVX2.</li> <li>Consulte [Recomendações do driver de codificador e decodificador de hardware](hardware-decoders-and-encoders.md) para uma lista de codificadores e decodificadores não compatíveis.</li><li>Ingressar em uma reunião usando a detecção de proximidade no Salas do Microsoft Teams requer o BLUETOOTH LE. O BLUETOOTH LE no Windows requer que o Bluetooth seja habilitado no dispositivo cliente e requer a versão de 64 bits do cliente do Teams. Este recurso não está disponível em clientes do Teams de 32 bits.</li></ul> |
|Eventos ao vivo do Teams | Se estiver produzindo um evento do Teams em tempo real, recomendamos o uso de um computador com um processador Core i5 Kaby Lake, 4,0 GB de RAM (ou superior) e o codificador de hardware. Consulte [Recomendações do driver de decodificador e codificador de hardware](hardware-decoders-and-encoders.md) para obter uma lista de codificadores e decodificadores **não compatíveis**. |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Requisitos de hardware para o Teams no Mac

| Componente | Requisito |
|---------|---------|
|Computador e processador    | Processador Intel Core Duo |
|Memória     |   4,0 GB de RAM|
|Disco rígido    |   1,5 GB de espaço em disco disponível      |
|Display    | Resolução de 1280 x 800 ou superior    |
|Sistema operacional  |    Uma das três versões mais recentes do macOS. Você pode encontrar informações sobre as versões mais recentes do macOS e como atualizar a sua versão do macOS [aqui](https://support.apple.com/en-us/HT201260). Por exemplo, quando uma nova versão do macOS é lançada, a nova versão e as duas imediatamente antes dela se tornam as versões com suporte.      |
|Vídeo  |    Webcam compatível      |
|Voz    |  Microfone e alto-falantes compatíveis, headset com microfone ou dispositivos equivalentes.       |
|Chamadas de vídeo e reuniões | <ul><li>Requer processador de dois núcleos. Para maior resolução de compartilhamento de vídeo/tela e taxa de quadros, um processador de quatro núcleos ou melhor é recomendado. </li><li>Ingressar em uma reunião usando a detecção de proximidade em um Microsoft Sala do Teams requer Bluetooth LE. O Bluetooth LE requer que o Bluetooth seja habilitado no dispositivo cliente.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Requisitos de hardware para o Teams no Linux

> [!NOTE]
> O Teams Desktop no Linux será desativado em dezembro de 2022.

| Componente | Requisito |
|---------|---------|
|Computador e processador    | 1,6 GHz (ou superior) (32 bits ou 64 bits), 2 núcleos        |
|Memória     |    4,0 GB de RAM |
|Disco rígido    | 3 GB de espaço em disco disponível        |
|Display    |   Resolução de tela 1024 x 768 |
|Hardware gráfico |  128 MB de memória gráfica
|Sistema operacional  | Distribuição Linux capaz de instalar o DEB ou o RPM. |
|Vídeo    |  Câmera de vídeo USB 2.0       |
|Dispositivos    |   Câmera de notebook, microfone e alto-falantes padrão    |
|Voz    |  Microfone e alto-falantes compatíveis, headset com microfone ou dispositivos equivalentes.       |
|Chamadas de vídeo e reuniões | <ul><li>Requer processador de dois núcleos. Para maior resolução de compartilhamento de vídeo/tela e taxa de quadros, um processador de quatro núcleos ou melhor é recomendado.</li><li>Ingressar em uma reunião usando a detecção de proximidade em uma sala do Microsoft Teams não está disponível no Linux.</li></ul>
|Distribuições do Linux compatíveis | Ubuntu 18,04 LTS, 20,04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8       |
|Ambiente da área de trabalho compatível | GNOME, KDE       |
|Servidor de exibição compatível | X11       |

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Requisitos de hardware para o Teams em dispositivos móveis

Você pode usar o Teams nas seguintes plataformas móveis:

- Android: compatível com telefones e tablets Android.

  O suporte é limitado às **últimas quatro** versões principais do Android. Por exemplo, quando uma nova versão principal do Android é lançada, o requisito do Android é a nova versão e as três versões mais recentes que a antecedem.

- iOS: compatível com iPhone, iPad e iPod Touch.

  O suporte é limitado às **duas** versões principais mais recentes do iOS. Por exemplo, quando uma nova versão principal do iOS é lançada, o requisito do iOS é a nova versão e as versões mais recentes que a antecedem. O efeito de vídeo opcional **Desfocar minha tela de fundo** no iOS exige um sistema operacional do iOS 12 ou posterior e é compatível com os seguintes dispositivos: iPhone 7 ou posterior, iPad 2018 (6ª geração) ou posterior e o iPod Touch 2019 (7ª geração).

> [!Note]
> Para obter uma melhor experiência no Teams, use a versão mais recente do iOS e Android.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Requisitos de hardware do Teams em um ambiente VDI (Virtual Desktop Infrastructure)

Confira [Teams para Virtualized Desktop Infrastructure](teams-for-vdi.md) para obter os requisitos para executar o Teams em um ambiente virtualizado.

### <a name="related-topics"></a>Tópicos relacionados

- [Obter o Aplicativos do Teams](get-clients.md)
- [Microsoft Teams em dispositivos móveis](https://support.microsoft.com/office/set-up-your-teams-mobile-apps-1ba8dce3-1122-47f4-8db6-00a4f93117e8)
- [Instalar o aplicativo Microsoft Teams usando um MSI](msi-deployment.md)
- [Limites e especificações do Microsoft Teams](limits-specifications-teams.md)
