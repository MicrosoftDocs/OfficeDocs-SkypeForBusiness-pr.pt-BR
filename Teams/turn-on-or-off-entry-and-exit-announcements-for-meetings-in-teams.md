---
title: Ativar ou desativar anúncios de entrada e saída para reuniões no Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: O administrador pode aprender sobre como ativar ou desativar anúncios de entrada e saída em uma reunião Microsoft Teams local.
ms.openlocfilehash: ab69b64352508d15b5f1125629ab90b3ec58f851
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60537272"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a>Ativar ou desativar anúncios de entrada e de saída para reuniões no Microsoft Teams

Ao configurar a Audioconferência em Microsoft 365 ou Office 365, você receberá uma ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone que as pessoas usarão para ligar para uma reunião do Microsoft Teams.
  
A ponte de conferência atende uma chamada feita por um usuário que discou para a reunião utilizando um telefone. A ponte de conferência atende o chamador com solicitações de voz de um atendedor automático de conferência e, dependendo das suas configurações, pode reproduzir notificações, pedir para o chamador gravar o nome dele e configurar a segurança do PIN. É fornecido um PIN para o organizador da reunião do Microsoft Teams que permite que ele inicie uma reunião se ele não conseguir iniciar usando o aplicativo Microsoft Teams. No entanto, você pode fazer a configuração de modo que o PIN não seja obrigatório para iniciar a reunião.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a>Definir as opções de participação da reunião

 **Usando o centro de administração do Microsoft Teams**

Você deve ser um administrador de serviço do Teams para fazer essas alterações. Veja [ Use funções de administrador Teams para gerenciar o Teams](./using-admin-roles.md) para ler sobre como obter funções e permissões de administrador.

1. Faça logoff no centro de administração.

2. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**.

3. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**.

4. No painel **Configurações da ponte**, ative ou desative **Notificações de entrada/saída de reuniões**. Esta opção é selecionada por padrão. Entretanto, se você a desmarcar, os usuários que já entraram na reunião não serão notificados quando alguém entrar ou sair da reunião.

5. Em **Tipo de anúncio de entrada/saída**, selecione **Nomes ou números de telefone** ou **Tons**.

   > [!NOTE]
   > Por padrão, os participantes externos não podem ver os números de telefone de participantes discados. Se você quiser manter a privacidade desses números de telefone, selecione **Tons** para o **tipo de anúncio de entrada/saída** (isso impede que os números sejam lidos pelas equipes).

6. Caso escolha **Nomes ou números de telefone**, ative ou desative **Solicitar que os chamadores gravem seu nome antes de entrar na reunião**.

7. Clique em **Salvar**.

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre Windows PowerShell

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

- [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="related-topics"></a>Tópicos relacionados

[Perguntas comuns sobre a Audioconferência](audio-conferencing-common-questions.md)