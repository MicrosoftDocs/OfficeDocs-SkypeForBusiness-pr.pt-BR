---
title: Requisitos de hardware para o aplicativo Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/04/2019
audience: Admin
ms.topic: reference
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre os requisitos de hardware necessários para instalar e executar o Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 753e134e34c68ab139819d8eaffb0ebfeac571cd
ms.sourcegitcommit: aad6c02b172a1412d3523a3cb3b3400423c0c3e0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2019
ms.locfileid: "38670188"
---
# <a name="hardware-requirements-for-the-microsoft-teams-app"></a>Requisitos de hardware para o aplicativo Microsoft Teams

Todos os requisitos nas seções a seguir se aplicam ao aplicativo da área de trabalho Teams e ao aplicativo Web Teams.

## <a name="hardware-requirements-for-the-teams-desktop-app-on-a-windows-pc"></a>Requisitos de hardware para o aplicativo da área de trabalho Teams em um computador Windows

|**Componente**|**Requisito**  |
|---------|---------|
|Computador e processador    | Mínimo de 1,6 GHz (ou mais) (32 bits ou 64 bits).        |
|Memória     |    2,0 GB DE RAM     |
|Disco rígido    | 3,0 GB de espaço disponível em disco        |
|Exibir    |   resolução de tela x 768 de 1024 |
|Hardware gráfico |  Mínimo de 128 MB de memória gráfica
|Sistema operacional  |    Windows 10, Windows 8,1 ou Windows 7 Service Pack 1 em 32 bits e 64 bits. Para obter a melhor experiência, use a versão mais recente de qualquer sistema operacional.|
|Versão do .NET    |  Requer o .NET 4,5 CLR ou posterior       |
|Vídeo    |  Câmera de vídeo USB 2,0       |
|Dispositivos    |   Câmera de laptop padrão, microfone e alto-falantes    | 
|Reuniões e chamadas com vídeo | Para ter uma experiência melhor com chamadas com vídeo e reuniões online, recomendamos usar um computador com um processador de 2,0 GHz e 4,0 GB de RAM (ou superior). O desfoque opcional meu efeito de vídeo **em segundo plano** requer um processador com suporte a Advanced vector Extensions 2 (AVX2). Consulte [recomendações de driver](hardware-decoders-and-encoders.md) de codificador e codificador de hardware para obter uma lista de codificadores e codificadores sem suporte. |
|Eventos ao vivo do Teams | Se você estiver produzindo um evento ao vivo do Teams, recomendamos usar um computador com um processador Core i5 KABY Lake, 4,0 GB de RAM (ou superior) e codificador de hardware. Consulte [recomendações de driver](hardware-decoders-and-encoders.md) de codificador e codificador de hardware para obter uma lista de codificadores e codificadores sem suporte. |

## <a name="hardware-requirements-for-the-teams-desktop-app-on-a-mac"></a>Requisitos de hardware para o aplicativo da área de trabalho Teams em um Mac

|**Componente**|**Requisito**  |
|---------|---------|
|631    | Processador Intel mínimo, Core 2 Duo ou superior |
|Memória     |   2,0 GB DE RAM      |
|Disco rígido    |   1,5 GB de espaço disponível em disco      |
|Exibir    | 1280 x 800 ou maior resolução    |
|Sistema operacional  |    Mac OS X 10,11 El Capitan ou posterior     |
|Vídeo  |    Webcam compatível     |
|Voz    |  Microfone e alto-falantes compatíveis, fone de ouvido com microfone ou dispositivo equivalente       |
|Reuniões e chamadas com vídeo | Para melhor experiência com chamadas com vídeo e reuniões online, recomendamos usar um computador com um processador de 2,0 GHz e 4,0 GB de RAM (ou superior). O desfoque opcional meu efeito de vídeo em segundo plano requer um processador com suporte a Advanced vector Extensions 2 (AVX2), compatível nos mais recentes dispositivos Mac do 2013 e mais tarde. Consulte [recomendações de driver](hardware-decoders-and-encoders.md) de codificador e codificador de hardware para obter uma lista de codificadores e codificadores sem suporte.|

## <a name="hardware-requirements-for-the-teams-desktop-app-on-a-linux"></a>Requisitos de hardware para o aplicativo da área de trabalho Teams em um Linux

|**Componente**|**Requisito**  |
|---------|---------|
|Computador e processador    | Mínimo de 1,6 GHz (ou mais) (32 bits ou 64 bits).        |
|Memória     |    2,0 GB DE RAM     |
|Disco rígido    | 3,0 GB de espaço disponível em disco        |
|Exibir    |   resolução de tela x 768 de 1024 |
|Hardware gráfico |  Mínimo de 128 MB de memória gráfica
|Sistema operacional  | Distribuição do Linux capaz de instalar o DEB ou o RPM. |
|Vídeo    |  Câmera de vídeo USB 2,0       |
|Dispositivos    |   Câmera de laptop padrão, microfone e alto-falantes    | 
|Voz    |  Microfone e alto-falantes compatíveis, fone de ouvido com microfone ou dispositivo equivalente       |
|Reuniões e chamadas com vídeo | Para melhor experiência com chamadas com vídeo e reuniões online, recomendamos usar um computador com um processador de 2,0 GHz e 4,0 GB de RAM (ou superior). O desfoque opcional meu efeito de vídeo em segundo plano requer um processador com suporte a Advanced vector Extensions 2 (AVX2), compatível nos mais recentes dispositivos Mac do 2013 e mais tarde. Consulte [recomendações de driver](hardware-decoders-and-encoders.md) de codificador e codificador de hardware para obter uma lista de codificadores e codificadores sem suporte.
|Distribuições Linux com suporte | Ubuntu 16, 4 LTS *, 18, 4 LTS, Fedora 30 Workstation, RHEL 8 Workstation, CentOS 8

* Etapas de pré-requisito para instalar o Ubuntu 16, 4 LTS que adiciona um repositório com versões mais recentes do libc + + (e compilador etc.) e atualiza libc + +:
```
sudo add-apt-repository ppa:ubuntu-toolchain-r/test
sudo apt-get update
sudo apt-get upgrade
```

## <a name="hardware-requirements-for-the-teams-app-on-mobile-devices"></a>Requisitos de hardware para o aplicativo Teams em dispositivos móveis

Você pode usar o Microsoft Teams nestas plataformas móveis:

- Android – requer Android 5,0 ou posterior. Compatível com telefones e tablets Android.

  O suporte limita-se às quatro últimas versões principais do Android. Quando uma nova versão principal do Android é lançada, a nova versão e as três versões anteriores são oficialmente aceitas.

- iOS – requer iOS 10,0 ou posterior. Compatível com iPhone, iPad e iPod Touch. 

  O suporte limita-se às duas versões principais mais recentes do iOS. Quando uma nova versão principal do iOS é liberada, a nova versão do iOS e da versão anterior é suportada oficialmente.

Para obter a melhor experiência com o Microsoft Teams, use a versão mais recente do iOS e Android.

## <a name="hardware-requirements-for-the-teams-app-in-a-virtual-desktop-infrastructure-vdi-environment"></a>Requisitos de hardware para o aplicativo Teams em um ambiente VDI (infraestrutura de área de trabalho virtual)

Consulte [Teams for Virtual Desktop Infrastructure](teams-for-vdi.md) para obter os requisitos para o Teams em execução em um ambiente virtualizado. 

### <a name="related-topics"></a>Tópicos relacionados
- [Obter aplicativos do teams](get-clients.md)
- [Microsoft Teams em dispositivos móveis](https://support.office.com/article/Microsoft-Teams-on-mobile-devices-2ACBCF73-8FD4-4929-9B31-AE403B88C2D3)
- [Instalar o aplicativo Microsoft Teams usando um MSI](msi-deployment.md)
