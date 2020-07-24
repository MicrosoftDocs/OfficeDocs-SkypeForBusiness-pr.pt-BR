---
title: Requisitos de hardware para o Microsoft Teams
ms.reviewer: microthk, sthurlow
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Neste artigo, você vai saber mais sobre os requisitos de hardware necessários para instalar e executar o Microsoft Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1a61c7338c6a182b6803bf2a302522b7fb97586f
ms.sourcegitcommit: 95ccfce5016dfda1a59812df446824be21f3f23e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/15/2020
ms.locfileid: "45143772"
---
# <a name="hardware-requirements-for-microsoft-teams"></a>Requisitos de hardware para o Microsoft Teams

Todos os requisitos das seções a seguir se aplicam aos aplicativos da área de trabalho do Microsoft Teams e do aplicativo Web da equipe.

## <a name="hardware-requirements-for-teams-on-a-windows-pc"></a>Requisitos de hardware para o Teams em um computador Windows

| Componente | Requisito |
|---------|---------|
|Computador e processador    | Mínimo de 1,6 GHz (ou superior) (32 bits ou 64 bits).        |
|Memória     |    2 GB de RAM     |
|Disco rígido    | 3 GB de espaço em disco disponível        |
|Display    |   Resolução de tela 1024 x 768 |
|Hardware gráfico |  Mínimo de 128 MB de memória gráfica
|Sistema operacional  |    Windows Server 2012 R2+, Windows 10 ou Windows 8.1 de 32 bits e 64 bits. Para obter uma melhor experiência, use a versão mais recente do sistema operacional.|
|Versão do .NET    |  Exige .NET 4.5 CLR ou posterior       |
|Vídeo    |  Câmera de vídeo USB 2.0       |
|Dispositivos    |   Câmera de notebook, microfone e alto-falantes padrão    | 
|Chamadas de vídeo e reuniões | <ul><li>Para uma experiência melhor com chamadas de vídeo entre duas pessoas, recomendamos o uso de um computador com um processador dual core e 4 GB de RAM (ou superior). </li><li>Para uma experiência melhor com reuniões online, recomendamos o uso de um computador com um processador dual core e 8.0 GB de RAM (ou superior). </li><li>Os **efeitos de vídeo de plano de fundo** opcionais não têm suporte em processadores sem um conjunto de instruções AVX2 sendo executado no Windows 8.1 ou abaixo.</li><li>Confira [Recomendações do driver de decodificador e codificador de hardware](hardware-decoders-and-encoders.md)para uma lista de codificadores e decodificadores não compatíveis.</li><li>Ingressar em uma reunião usando a detecção de proximidade em uma sala do Microsoft Teams requer o Bluetooth LE, que exige que o Bluetooth esteja habilitado no dispositivo cliente e para clientes Windows é necessário o cliente do Teams de 64 bits. Ela não está disponível em clientes do Teams de 32 bits.</li></ul> |
|Eventos ao vivo do Teams | Se estiver produzindo um evento do Teams em tempo real, recomendamos o uso de um computador com um processador Core i5 Kaby Lake, 4 GB de RAM (ou superior) e o codificador de hardware. Confira [Recomendações do driver de decodificador e codificador de hardware](hardware-decoders-and-encoders.md)para uma lista de codificadores e decodificadores não compatíveis. |

## <a name="hardware-requirements-for-teams-on-a-mac"></a>Requisitos de hardware para o Teams no Mac

| Componente | Requisito |
|---------|---------|
|Processador    | Processador Intel Core 2 Duo ou superior |
|Memória     |   2 GB de RAM      |
|Disco rígido    |   1,5 GB de espaço em disco disponível      |
|Display    | Resolução de 1280 x 800 ou superior    |
|Sistema operacional  |    Mac OS X 10.11 El Capitan ou posterior     |
|Vídeo  |    Webcam compatível      |
|Voz    |  Microfone e alto-falantes compatíveis, headset com microfone ou dispositivos equivalentes.       |
|Chamadas de vídeo e reuniões | <ul><li>Para uma experiência melhor com chamadas de vídeo entre duas pessoas, recomendamos o uso de um computador com um processador dual core e 4 GB de RAM (ou superior). </li><li>Para uma experiência melhor com reuniões online, recomendamos o uso de um computador com um processador dual core e 8.0 GB de RAM (ou superior).</li><li>Confira [Recomendações do driver de decodificador e codificador de hardware](hardware-decoders-and-encoders.md)para uma lista de codificadores e decodificadores não compatíveis.</li><li>Ingressar em uma reunião usando a detecção de proximidade em uma sala do Microsoft Teams não está disponível no Mac OS.</li></ul> |

## <a name="hardware-requirements-for-teams-on-linux"></a>Requisitos de hardware para o Teams no Lixus

| Componente | Requisito |
|---------|---------|
|Computador e processador    | Mínimo de 1,6 GHz (ou superior) (32 bits ou 64 bits).        |
|Memória     |    2 GB de RAM     |
|Disco rígido    | 3 GB de espaço em disco disponível        |
|Display    |   Resolução de tela 1024 x 768 |
|Hardware gráfico |  Mínimo de 128 MB de memória gráfica
|Sistema operacional  | Distribuição Linux capaz de instalar o DEB ou o RPM. |
|Vídeo    |  Câmera de vídeo USB 2.0       |
|Dispositivos    |   Câmera de notebook, microfone e alto-falantes padrão    | 
|Voz    |  Microfone e alto-falantes compatíveis, headset com microfone ou dispositivos equivalentes.       |
|Chamadas de vídeo e reuniões | <ul><li>Para uma experiência melhor com chamadas de vídeo entre duas pessoas, recomendamos o uso de um computador com um processador dual core e 4 GB de RAM (ou superior). </li><li>Para uma experiência melhor com reuniões online, recomendamos o uso de um computador com um processador dual core e 8.0 GB de RAM (ou superior).</li><li>Para obter uma lista de codificadores e decodificadores não compatíveis, confira [Recomendações do driver de decodificador e codificador de hardware](hardware-decoders-and-encoders.md).</li><li>Ingressar em uma reunião usando a detecção de proximidade em uma sala do Microsoft Teams não está disponível no Linux.</li></ul>
|Distribuições do Linux compatíveis | Ubuntu 16.04 LTS, 18.04 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8

## <a name="hardware-requirements-for-teams-on-mobile-devices"></a>Requisitos de hardware para o Teams em dispositivos móveis

Você pode usar o Teams nas seguintes plataformas móveis:

- Android: compatível com telefones e tablets Android.

  O suporte é limitado às últimas quatro versões principais do Android. Quando uma nova versão principal do Android é lançada, a nova versão e as três versões anteriores são oficialmente suportadas.

- iOS: compatível com iPhone, iPad e iPod Touch.

  O suporte é limitado às duas versões principais mais recentes do iOS. Quando uma nova versão principal do iOS é lançada, a nova versão do iOS e a versão anterior são oficialmente suportadas.
  O efeito de vídeo opcional **Desfocar minha tela de fundo** no iOS exige um sistema operacional do iOS 12 ou posterior e é compatível com os seguintes dispositivos: iPhone 7 ou posterior, iPad 2018 (6ª geração) ou posterior e o iPod Touch 2019 (7ª geração).

Para obter uma melhor experiência no Teams, use a versão mais recente do iOS e Android.

## <a name="hardware-requirements-for-teams-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Requisitos de hardware do Teams em um ambiente VDI (Virtual Desktop Infrastructure)

Confira [Teams para Virtualized Desktop Infrastructure](teams-for-vdi.md) para obter os requisitos para executar o Teams em um ambiente virtualizado.

### <a name="related-topics"></a>Tópicos relacionados
- [Obter o Aplicativos do Teams](get-clients.md)
- [Microsoft Teams em dispositivos móveis](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Instalar o aplicativo Microsoft Teams usando um MSI](msi-deployment.md)
- [Limites e especificações do Microsoft Teams](limits-specifications-teams.md)
