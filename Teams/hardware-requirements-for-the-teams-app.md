---
title: Requisitos de hardware para o Microsoft Teams
ms.reviewer: microthk, sthurlow
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
localization_priority: Priority
search.appverid: MET150
description: Neste artigo, você aprenderá sobre os requisitos de hardware necessários para instalar e executar o Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7de101954a9947fc5edeff43aff27d011e75dc387c25fa53f7190ce5a4a52256
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54336161"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Requisitos de hardware para o Microsoft Teams

Todos os requisitos das seções a seguir se aplicam aos aplicativos da área de trabalho do Microsoft Teams e do aplicativo Web da equipe.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Requisitos de hardware para o Teams em um computador Windows

| Componente | Requisito |
|---------|---------|
|Computador e processador    | Mínimo de 1,1 GHz ou superior, 2 núcleos<br><br>Observação: para processadores Intel, deve ser considerada a velocidade máxima atingida usando a tecnologia Intel Note Plus (Max Note Frequency)         |
|Memória     |    4,0 GB de RAM (o Teams requer 4 GB de RAM dedicados além de quaisquer outros requisitos do sistema)    |
|Disco rígido    | 3 GB de espaço em disco disponível        |
|Display    |   Resolução de tela 1024 x 768 |
|Hardware gráfico |  Sistema Operacional Windows: a aceleração de hardware de elementos gráficos requer o DirectX 9 ou posterior, com o WDDM 2.0 ou superior para Windows 10 (ou WDDM 1.3 ou superior para Windows 10 Fall Creators Update)
|Sistema operacional  |    Windows 10 (exceto Windows 10 LTSC), Windows 10 no ARM, Windows 8.1, Windows Server 2019, Windows Server 2016, Windows Server 2012 R2. Observação: Recomendamos usar a versão mais recente do Windows e os patches de segurança disponíveis.|
|Versão do .NET    |  Exige .NET 4.5 CLR ou posterior       |
|Vídeo    |  Câmera de vídeo USB 2.0       |
|Dispositivos    |   Câmera de notebook, microfone e alto-falantes padrão    |
|Chamadas de vídeo e reuniões|<ul><li>Requer um processador de 2 núcleos. Para maior resolução de vídeo/compartilhamento de tela e taxa de quadros, um processador de 4 núcleos ou superior é recomendado.</li> <li>Os efeitos de vídeo em tela de fundo exigem o Windows 10 ou um processador com o conjunto de instruções AVX2.</li> <li>Consulte [Recomendações do driver de codificador e decodificador de hardware](hardware-decoders-and-encoders.md) para uma lista de codificadores e decodificadores não compatíveis.</li><li>Ingressar em uma reunião usando a detecção de proximidade em uma Sala do Microsoft Teams requer o Bluetooth LE, que necessita que o Bluetooth esteja habilitado no dispositivo do cliente, e para clientes Windows também requer o cliente Teams de 64 bits. Este recurso não está disponível em clientes Teams de 32 bits.</li></ul> |
|Eventos ao vivo do Teams | Se estiver produzindo um evento do Teams em tempo real, recomendamos o uso de um computador com um processador Core i5 Kaby Lake, 4,0 GB de RAM (ou superior) e o codificador de hardware. Consulte [Recomendações do driver de decodificador e codificador de hardware](hardware-decoders-and-encoders.md) para obter uma lista de codificadores e decodificadores **não compatíveis**. |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Requisitos de hardware para o Teams no Mac

| Componente | Requisito |
|---------|---------|
|Computador e processador    | Processador Intel Core Duo |
|Memória     |   4,0 GB de RAM (o Teams requer 4 GB de RAM dedicados além de quaisquer outros requisitos do sistema)     |
|Disco rígido    |   1,5 GB de espaço em disco disponível      |
|Display    | Resolução de 1280 x 800 ou superior    |
|Sistema operacional  |    Uma das três versões mais recentes do macOS. Você pode encontrar informações sobre as versões mais recentes do macOS e como atualizar a sua versão do macOS [aqui](https://support.apple.com/pt-BR/HT201260). Por exemplo, quando uma nova versão do macOS é lançada, a nova versão e as duas imediatamente antes dela se tornam as versões com suporte.      |
|Vídeo  |    Webcam compatível      |
|Voz    |  Microfone e alto-falantes compatíveis, headset com microfone ou dispositivos equivalentes.       |
|Chamadas de vídeo e reuniões | <ul><li>Requer um processador de 2 núcleos. Para maior resolução de vídeo/compartilhamento de tela e taxa de quadros, um processador de 4 núcleos ou superior é recomendado. </li><li>Ingressar em uma reunião usando a detecção de proximidade em uma Sala do Microsoft Teams não está disponível no macOS.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Requisitos de hardware para o Teams no Linux

| Componente | Requisito |
|---------|---------|
|Computador e processador    | 1,6 GHz (ou superior) (32 bits ou 64 bits), 2 núcleos        |
|Memória     |    4,0 GB de RAM (o Teams requer 4 GB de RAM dedicados além de quaisquer outros requisitos do sistema)   |
|Disco rígido    | 3 GB de espaço em disco disponível        |
|Display    |   Resolução de tela 1024 x 768 |
|Hardware gráfico |  128 MB de memória gráfica
|Sistema operacional  | Distribuição Linux capaz de instalar o DEB ou o RPM. |
|Vídeo    |  Câmera de vídeo USB 2.0       |
|Dispositivos    |   Câmera de notebook, microfone e alto-falantes padrão    |
|Voz    |  Microfone e alto-falantes compatíveis, headset com microfone ou dispositivos equivalentes.       |
|Chamadas de vídeo e reuniões | <ul><li>Requer um processador de 2 núcleos. Para maior resolução de vídeo/compartilhamento de tela e taxa de quadros, um processador de 4 núcleos ou superior é recomendado.</li><li>Ingressar em uma reunião usando a detecção de proximidade em uma sala do Microsoft Teams não está disponível no Linux.</li></ul>
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
- [Microsoft Teams em dispositivos móveis](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Instalar o aplicativo Microsoft Teams usando um MSI](msi-deployment.md)
- [Limites e especificações do Microsoft Teams](limits-specifications-teams.md)
