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
localization_priority: Normal
search.appverid: MET150
description: Neste artigo, você aprenderá sobre os requisitos de hardware necessários para instalar e executar o Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0555296da359a916b512bde878d5c87207a6e549
ms.sourcegitcommit: 48cb3cdd69558ec80f8f25f870b302a65280ce5a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2020
ms.locfileid: "48389879"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Requisitos de hardware para o Microsoft Teams

Todos os requisitos das seções a seguir se aplicam aos aplicativos da área de trabalho do Microsoft Teams e do aplicativo Web da equipe.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Requisitos de hardware para o Teams em um computador Windows

| Componente | Requisito |
|---------|---------|
|Computador e processador    | Mínimo de 1,6 GHz (ou mais), 2 núcleo        |
|Memória     |    4,0 GB DE RAM     |
|Disco rígido    | 3 GB de espaço em disco disponível        |
|Display    |   Resolução de tela 1024 x 768 |
|Hardware gráfico |  Sistema operacional Windows: a aceleração de hardware gráfico requer o DirectX 9 ou posterior, com o WDDM 2,0 ou superior para Windows 10 (ou WDDM 1,3 ou superior para atualização do Windows 10 para criadores de outono)
|Sistema operacional  |    Windows 10, Windows 10 em ARM, Windows 8,1, Windows Server 2019, Windows Server 2016|
|Versão do .NET    |  Exige .NET 4.5 CLR ou posterior       |
|Vídeo    |  Câmera de vídeo USB 2.0       |
|Dispositivos    |   Câmera de notebook, microfone e alto-falantes padrão    |
|Chamadas de vídeo e reuniões|<ul><li>Requer processador de 2 núcleos. Para obter maior resolução de vídeo/tela e a taxa de quadros, é recomendável um processador de 4 núcleos ou melhor.</li> <li>Para obter uma lista de codificadores e decodificadores não compatíveis, confira [Recomendações do driver de decodificador e codificador de hardware](hardware-decoders-and-encoders.md).</li><li>Ingressar em uma reunião usando a detecção de proximidade em uma sala do Microsoft Teams requer Bluetooth LE, o que requer que o Bluetooth esteja habilitado no dispositivo cliente e para clientes Windows também requer o cliente da equipe de 64 bits. Este recurso não está disponível em clientes da equipe de 32 bits.</li></ul> |
|Eventos ao vivo do Teams | Se você estiver produzindo um evento ao vivo do Teams, recomendamos usar um computador com um processador Core i5 KABY Lake, 4,0-GB de RAM (ou superior) e codificador de hardware. Consulte [recomendações de driver](hardware-decoders-and-encoders.md) de codificador e codificador de hardware para obter uma lista de codificadores e codificadores **sem suporte** . |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Requisitos de hardware para o Teams no Mac

| Componente | Requisito |
|---------|---------|
|Computador e processador    | Processador Intel Core Duo |
|Memória     |   4,0 GB DE RAM      |
|Disco rígido    |   1,5 GB de espaço em disco disponível      |
|Display    | Resolução de 1280 x 800 ou superior    |
|Sistema operacional  |    Uma das três versões mais recentes do macOS. Você pode encontrar as versões mais recentes do macOS [aqui](https://support.apple.com/en-us/HT201260). Por exemplo, quando uma nova versão do macOS é liberada, a nova versão e as duas imediatamente precedentes tornam-se as versões com suporte.      |
|Vídeo  |    Webcam compatível      |
|Voz    |  Microfone e alto-falantes compatíveis, headset com microfone ou dispositivos equivalentes.       |
|Chamadas de vídeo e reuniões | <ul><li>Requer processador de 2 núcleos. Para obter maior resolução de vídeo/tela e a taxa de quadros, é recomendável um processador de 4 núcleos ou melhor. </li><li>Ingressar em uma reunião usando a detecção de proximidade em uma sala do Microsoft Teams não está disponível no macOS.</li></ul>
|

## <a name="hardware-requirements-for-teams-on-linux"></a>Requisitos de hardware para o Teams no Linux

| Componente | Requisito |
|---------|---------|
|Computador e processador    | 1,6 GHz (ou superior) (32 bits ou 64 bits), 2 núcleo        |
|Memória     |    4,0 GB DE RAM     |
|Disco rígido    | 3 GB de espaço em disco disponível        |
|Display    |   Resolução de tela 1024 x 768 |
|Hardware gráfico |  memória gráfica de 128 MB
|Sistema operacional  | Distribuição Linux capaz de instalar o DEB ou o RPM. |
|Vídeo    |  Câmera de vídeo USB 2.0       |
|Dispositivos    |   Câmera de notebook, microfone e alto-falantes padrão    |
|Voz    |  Microfone e alto-falantes compatíveis, headset com microfone ou dispositivos equivalentes.       |
|Chamadas de vídeo e reuniões | <ul><li>Requer processador de 2 núcleos. Para obter maior resolução de vídeo/tela e a taxa de quadros, é recomendável um processador de 4 núcleos ou melhor.</li><li>Ingressar em uma reunião usando a detecção de proximidade em uma sala do Microsoft Teams não está disponível no Linux.</li></ul>
|Distribuições do Linux compatíveis | Ubuntu 16.04 LTS, 18.04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Requisitos de hardware para o Teams em dispositivos móveis

Você pode usar o Teams nas seguintes plataformas móveis:

- Android: compatível com telefones e tablets Android.

  O suporte limita-se às **quatro últimas** versões principais do Android. Por exemplo, quando uma nova versão principal do Android for lançada, o requisito do Android será a nova versão e as três versões mais recentes que a precedem.

- iOS: compatível com iPhone, iPad e iPod Touch.

  O suporte limita-se às **duas** versões principais mais recentes do Ios. Por exemplo, quando uma nova versão principal do iOS é liberada, o requisito do iOS é a nova versão e as versões mais recentes que a precedem. O **Desfoque opcional meu** efeito de vídeo em segundo plano no Ios exige um sistema operacional do IOS 12 ou posterior, compatível com os seguintes dispositivos: iPhone 7 ou posterior, iPad 2018 (6º geração) ou posterior e iPod Touch 2019 (7 geração).

> [!Note]
> Para obter uma melhor experiência no Teams, use a versão mais recente do iOS e Android.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Requisitos de hardware do Teams em um ambiente VDI (Virtual Desktop Infrastructure)

Confira [Teams para Virtualized Desktop Infrastructure](teams-for-vdi.md) para obter os requisitos para executar o Teams em um ambiente virtualizado.

### <a name="related-topics"></a>Tópicos relacionados

- [Obter o Aplicativos do Teams](get-clients.md)
- [Microsoft Teams em dispositivos móveis](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Instalar o aplicativo Microsoft Teams usando um MSI](msi-deployment.md)
- [Limites e especificações do Microsoft Teams](limits-specifications-teams.md)
