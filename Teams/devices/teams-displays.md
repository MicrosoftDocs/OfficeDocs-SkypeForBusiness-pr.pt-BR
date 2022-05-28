---
title: Microsoft Teams exibições
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
search.appverid: MET150
ms.localizationpriority: medium
description: Este artigo fornece uma visão geral dos recursos com suporte Microsoft Teams exibições.
ms.openlocfilehash: 4b724370ff348f41b8d4c4406a218e1dd1ba0709
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65760863"
---
# <a name="microsoft-teams-displays"></a>Microsoft Teams exibições

Microsoft Teams displays são uma categoria de dispositivos Teams dedicados que apresentam uma tela sensível ao toque ambiente e uma experiência de mãos livres da plataforma Cortana. Este artigo fornece uma visão geral Teams exibições e pode ajudá-lo a planejar, fornecer e gerenciar Teams exibições em sua organização.

Teams de vídeo reúne seus&ndash;recursos favoritos Teams chat, reuniões, chamadas, calendário e arquivos&ndash;em um único dispositivo. Com Teams telas, os usuários podem usar um microfone, câmera e alto-falantes (ou Bluetooth headset) para uma experiência confiável de chamada e reunião. Teams exibições se integram aos computadores Windows dos usuários para trazer uma experiência complementar que permite a interação perfeita entre dispositivos.

Para saber mais, confira Introdução [com Teams telas](https://support.microsoft.com/office/get-started-with-teams-displays-ff299825-7f13-4528-96c2-1d3437e6d4e6).

## <a name="features-supported-by-teams-displays"></a>Recursos compatíveis com Teams telas

Além dos recursos [compatíveis com Teams,](phones-for-teams.md#features-supported-by-teams-phones) os seguintes recursos são exclusivos Teams telas:

- **Exibições dedicadas para Teams** os usuários podem acessar todos os recursos Teams principais, incluindo chat, reuniões, chamadas, equipes e canais, arquivos e muito mais.
- **Experiência ambiente** Os usuários podem ficar facilmente no controle de seu trabalho com exibições sempre ativadas e relanceáveis para ver atividades e notificações importantes sem alternar o contexto em seu dispositivo de trabalho principal. Os usuários também podem personalizar Teams exibições personalizando a tela de fundo por meio de configurações.
- Mãos **livres com Cortana** Os usuários podem interagir com exibições do Teams usando sua voz para ingressar e apresentar com esforço em reuniões, ditar respostas a um chat do Teams, verificar o que está no calendário e muito mais.
- **Deixar uma anotação na tela de bloqueio** Os convidados podem optar por deixar anotações de áudio, vídeo e texto, e os usuários podem verificar as anotações deixadas pelos convidados e ver quem parou.  

## <a name="required-licenses"></a>Licenças necessárias

Teams licenças podem ser adquiridas como parte [de Microsoft 365 e Office 365 assinaturas](/office365/servicedescriptions/teams-service-description). Para saber mais sobre as licenças necessárias para usar Teams vídeo, consulte chamadas de voz e vídeo com [Microsoft Teams](https://products.office.com/microsoft-teams/voice-calling).

Para obter mais informações sobre como obter Teams, confira [Como fazer obter acesso ao Microsoft Teams?](https://support.office.com/article/fc7f1634-abd3-4f26-a597-9df16e4ca65b)

## <a name="deploy-teams-displays-using-intune"></a>Implantar Teams exibições usando Intune

Para saber mais sobre como implantar Teams exibições usando Intune, consulte Implantar Teams [e Teams telas](phones-displays-deploy.md).

## <a name="manage-teams-displays-in-your-organization"></a>Gerenciar Teams exibições em sua organização

Para gerenciar seus Teams de exibição, no painel de navegação esquerdo do centro de administração Microsoft Teams, vá para **Teams exibições**. A partir daqui, você pode alterar o perfil de configuração do dispositivo, gerenciar atualizações, reiniciar dispositivos, adicionar e remover marcas de dispositivo e muito mais. Para obter mais informações, [consulte Gerenciar seus dispositivos Teams](device-management.md).

## <a name="set-up-hot-desking-on-teams-displays"></a>Configurar o hot desking em Teams telas

O hot desking permite que as pessoas em sua organização reservem workspaces temporários com antecedência por meio de Teams e Outlook, ou do próprio dispositivo. Quando o hot desking está habilitado, os usuários Teams são exibidos com suas credenciais de Microsoft 365 para acessar suas reuniões, chats e arquivos. Quando eles sairem, todas as suas informações pessoais serão removidas do dispositivo.

Para começar, você precisará adquirir licenças Salas do Microsoft Teams Padrão e criar contas de recursos para cada Teams exibição. Consulte [Criar contas de recursos para salas e dispositivos Teams compartilhados](../rooms/with-office-365.md) para criar contas de recursos.

Depois de criar contas de recursos, você pode criar e atribuir uma política para habilitar o hot desking. Consulte [New-CsTeamsIPPhonePolicy](/powershell/module/skype/new-csteamsipphonepolicy?view=skype-ps) para saber mais.

> [!IMPORTANT]
> Como Teams exibições com mesa dinâmica são usadas em workspaces compartilhados por várias pessoas, as regras de Acesso Condicional e outras configurações de identidade em seu ambiente, como a Autenticação Multifator, podem afetar esses dispositivos e causar problemas de entrada. Para obter diretrizes sobre como proteger dispositivos compartilhados, consulte as práticas recomendadas de autenticação [para dispositivos Teams Android compartilhados](authentication-best-practices-for-android-devices.md).

## <a name="upgrade-teams-phones-to-teams-displays"></a>Atualizar Teams para Teams telas

Teams exibições é a evolução de Teams telefones. Você pode atualizar Teams em sua organização para Teams exibições usando o Microsoft Teams de administração. Essa opção está disponível somente para telefones que dão suporte à atualização para Teams telas. Para saber mais, confira [Atualizar Teams para Teams telas](upgrade-phones-to-displays.md).

## <a name="see-also"></a>Confira também

[Introdução Microsoft Teams telas](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/introducing-microsoft-teams-displays/ba-p/1505437)

[Teams Marketplace](https://office.com/teamsdevices)

[Telefones para o Teams](phones-for-teams.md)

[Telefones IP certificados para Microsoft Teams](teams-ip-phones.md)

[Atualizar telefones IP para Teams telas](upgrade-phones-to-displays.md)

[Cortana de voz no Teams](../cortana-in-teams.md)