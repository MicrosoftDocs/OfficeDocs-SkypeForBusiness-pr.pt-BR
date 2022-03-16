---
title: Microsoft Teams exibe
ms.author: czawideh
author: cazawideh
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: Este artigo fornece uma visão geral dos recursos e com suporte Microsoft Teams exibições.
ms.openlocfilehash: 77af5392b539045cdbacda2d6c278d35098437ed
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514674"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams exibe

Microsoft Teams displays são uma categoria de dispositivos de Teams exclusivos que apresentam uma tela sensível ao toque ambiente e uma experiência prática com Cortana. Este artigo fornece uma visão geral Teams exibições e pode ajudá-lo a planejar, entregar e gerenciar Teams exibições em sua organização.

Teams exibe seus recursos favoritos&ndash; Teams, reuniões, chamadas, calendário e arquivos&ndash; em um único dispositivo. Com Teams, os usuários podem usar microfone, câmera e alto-falantes (ou Bluetooth headset) para uma experiência confiável de chamada e reunião. Teams exibe integrações com os PCs Windows usuários para trazer uma experiência de companhia que permite a interação perfeita entre dispositivos.

Para saber mais, confira [Começar a Teams exibições](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Recursos suportados por Teams displays

Além dos recursos [suportados por telefones Teams](phones-for-teams.md#features-supported-by-teams-phones), os seguintes recursos são exclusivos Teams exibições:

- **Exibições dedicadas para Teams** Os usuários podem acessar todos os recursos Teams principais, incluindo chat, reuniões, chamadas, equipes e canais, arquivos e muito mais.
- **Experiência ambiente** Os usuários podem ficar sempre atentos ao trabalho com exibições sempre ativas e relances para ver atividades e notificações importantes sem alternar por contexto em seu dispositivo de trabalho principal. Os usuários também podem personalizar Teams exibições personalizando o plano de fundo por meio de configurações.
- **Mãos livres** com o Cortana Os usuários podem interagir com as exibições do Teams usando sua voz para ingressar e apresentar sem esforço nas reuniões, ditar respostas a um chat Teams, verificar o que está no calendário e muito mais.
- **Deixar uma observação na tela de bloqueio** Os convidados podem optar por deixar notas de áudio, vídeo e texto, e os usuários podem verificar as anotações deixadas pelos convidados e ver quem parou.  

## <a name="required-licenses"></a>Licenças necessárias

Teams licenças podem ser compradas como parte de Microsoft 365 [e Office 365 assinaturas](/office365/servicedescriptions/teams-service-description). Para saber mais sobre as licenças necessárias para usar Teams exibições, consulte [Voz e chamadas de vídeo com Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Para obter mais informações sobre como obter Teams, confira [Como obter acesso a Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Implantar Teams exibições usando o Intune

Para saber mais sobre como implantar Teams displays usando o Intune, consulte [Deploy Teams phones and Teams displays](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Gerenciar Teams exibições em sua organização

Para gerenciar seus Teams de exibição, na navegação à esquerda do centro de administração Microsoft Teams, vá para Teams **displays**. A partir daqui, você pode alterar o perfil de configuração do dispositivo, gerenciar atualizações, reiniciar dispositivos, adicionar e remover marcas de dispositivo e muito mais. Para obter mais informações, consulte [Manage your devices in Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurar o hot desking em Teams exibições

O hot desking permite que as pessoas em sua organização reservem espaços de trabalho temporários com antecedência por meio de Teams e Outlook, ou do próprio dispositivo. Quando o hot desking está habilitado, os usuários Teams são exibidos com suas credenciais Microsoft 365 para acessar suas reuniões, chats e arquivos. Quando eles sairem, todas as suas informações pessoais serão removidas do dispositivo.

Para começar, você precisará adquirir Salas do Microsoft Teams Padrão licenças e criar contas de recurso para cada Teams de exibição. Consulte [Create resource accounts for rooms and shared Teams devices](../rooms/with-office-365.md) to create resource accounts.

Depois de criar contas de recursos, você pode criar e atribuir uma política para habilitar o hot desking. Consulte [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) para saber mais.

> [!IMPORTANT]
> Como Teams exibições com hot desking são usadas em espaços de trabalho compartilhados por várias pessoas, as regras de Acesso Condicional e outras configurações de identidade em seu ambiente, como a Autenticação Multifacional, podem afetar esses dispositivos e causar problemas de entrada. Para obter orientações sobre como proteger dispositivos compartilhados, consulte [Práticas recomendadas de autenticação para dispositivos Teams Android compartilhados](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Atualizar Teams telefones para Teams displays

Teams é a evolução dos telefones Teams. Você pode atualizar Teams telefones em sua organização para Teams exibições usando o Microsoft Teams de administração. Essa opção está disponível somente para telefones que suportam a atualização para Teams displays. Para saber mais, confira [Atualizar Teams telefones para Teams displays](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Confira também

[Apresentando Microsoft Teams exibições](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Telefones para o Teams](phones-for-teams.md)

[Telefones IP certificados para Microsoft Teams](teams-ip-phones.md)

[Atualizar telefones IP para Teams displays](upgrade-phones-to-displays.md)

[Cortana de voz no Teams](../cortana-in-teams.md)