---
title: Exibições do Microsoft Teams
ms.author: dstrome
author: dstrome
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: Este artigo fornece uma visão geral dos recursos compatíveis com as exibições do Microsoft Teams.
ms.openlocfilehash: 18b8219a3eef391170c7321ae994d79f1b73f016
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67268766"
---
# <a name="microsoft-teams-displays"></a>Exibições do Microsoft Teams

As exibições do Microsoft Teams são uma categoria de todos os dispositivos teams dedicados que apresentam uma tela sensível ao toque ambiente e uma experiência de mãos livres da Cortana. Este artigo fornece uma visão geral das exibições do Teams e pode ajudá-lo a planejar, entregar e gerenciar as exibições do Teams em sua organização.

As exibições do Teams reúnem seus recursos favoritos de chat, reuniões, chamadas, calendário e arquivos do&ndash;Teams&ndash;em um único dispositivo. Com as exibições do Teams, os usuários podem usar um microfone, câmera e alto-falantes (ou headset Bluetooth) para uma experiência confiável de chamada e reunião. As exibições do Teams se integram aos computadores Windows dos usuários para trazer uma experiência complementar que permite uma interação perfeita entre dispositivos.

Para saber mais, confira Introdução [às exibições do Teams](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Recursos compatíveis com exibições do Teams

Além dos recursos [compatíveis com telefones do Teams](phones-for-teams.md#features-supported-by-teams-phones), os seguintes recursos são exclusivos para exibições do Teams:

- **Exibições dedicadas para o Teams** Os usuários podem acessar todos os principais recursos do Teams, incluindo chat, reuniões, chamadas, equipes e canais, arquivos e muito mais.
- **Experiência ambiente** Os usuários podem ficar facilmente no controle de seu trabalho com exibições sempre ativadas e relanceáveis para ver atividades e notificações importantes sem alternar o contexto em seu dispositivo de trabalho principal. Os usuários também podem personalizar as exibições do Teams personalizando o plano de fundo por meio de configurações.
- **Mãos livres com a Cortana** Os usuários podem interagir com as exibições do Teams usando sua voz para ingressar e apresentar-se facilmente em reuniões, ditar respostas a um chat do Teams, verificar o que está no calendário e muito mais.
- **Deixar uma anotação na tela de bloqueio** Os convidados podem optar por deixar anotações de áudio, vídeo e texto, e os usuários podem verificar as anotações deixadas pelos convidados e ver quem parou.  

## <a name="required-licenses"></a>Licenças necessárias

As licenças do Teams podem ser adquiridas como parte das [assinaturas do Microsoft 365 e Office 365 cliente](/office365/servicedescriptions/teams-service-description). Para saber mais sobre as licenças necessárias para usar as exibições do Teams, consulte chamadas de voz [e vídeo com o Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Para obter mais informações sobre como obter o Teams, confira [Como fazer obter acesso ao Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Implantar exibições do Teams usando Intune

Para saber mais sobre como implantar as exibições do Teams usando Intune, consulte [Implantar telefones do Teams e exibições do Teams](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Gerenciar exibições do Teams em sua organização

Para gerenciar os dispositivos de exibição do Teams, no painel de navegação esquerdo do Centro de administração do Microsoft Teams, vá para as exibições **do Teams**. A partir daqui, você pode alterar o perfil de configuração do dispositivo, gerenciar atualizações, reiniciar dispositivos, adicionar e remover marcas de dispositivo e muito mais. Para obter mais informações, consulte [Gerenciar seus dispositivos no Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurar o hot desking em exibições do Teams

O hot desking permite que as pessoas em sua organização reservem workspaces temporários com antecedência por meio do Teams e do Outlook ou do próprio dispositivo. Quando o hot desking estiver habilitado, os usuários entrarão no Teams com suas credenciais do Microsoft 365 para acessar suas reuniões, chats e arquivos. Quando eles sairem, todas as suas informações pessoais serão removidas do dispositivo.

Para começar, você precisará adquirir licenças Salas do Microsoft Teams Padrão e criar contas de recursos para cada exibição do Teams. Consulte [Criar contas de recursos para salas e dispositivos compartilhados do Teams](../rooms/with-office-365.md) para criar contas de recursos.

Depois de criar contas de recursos, você pode criar e atribuir uma política para habilitar o hot desking. Consulte [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) para saber mais.

> [!IMPORTANT]
> Como as exibições do Teams com mesa dinâmica são usadas em workspaces compartilhados por várias pessoas, as regras de Acesso Condicional e outras configurações de identidade em seu ambiente, como a Autenticação Multifator, podem afetar esses dispositivos e causar problemas de entrada. Para obter diretrizes sobre como proteger dispositivos compartilhados, consulte as práticas recomendadas de autenticação [para dispositivos Android compartilhados do Teams](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Atualizar telefones do Teams para exibições do Teams

As exibições do Teams são a evolução dos telefones do Teams. Você pode atualizar telefones do Teams em sua organização para exibições do Teams usando o centro de administração do Microsoft Teams. Essa opção está disponível somente para telefones que dão suporte à atualização para exibições do Teams. Para saber mais, consulte [Atualizar telefones do Teams para exibições do Teams](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Confira também

[Apresentação de exibições do Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Telefones para o Teams](phones-for-teams.md)

[Telefones IP certificados para o Microsoft Teams](teams-ip-phones.md)

[Atualizar telefones IP para exibições do Teams](upgrade-phones-to-displays.md)

[Assistência de voz da Cortana no Teams](../cortana-in-teams.md)