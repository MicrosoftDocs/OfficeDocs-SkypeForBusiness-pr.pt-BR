---
title: Gerenciar o aplicativo Turnos para sua organização no Microsoft Teams
author: kenwith
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: Aprenda a configurar e gerenciar o aplicativo desloca em equipes para trabalhadores de firstline em sua organização.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fdb34f0cc1df67350ec5224e02d5922d49b2663f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891632"
---
# <a name="manage-the-shifts-app-for-your-organization-in-microsoft-teams"></a>Gerenciar o aplicativo Turnos para sua organização no Microsoft Teams

> [!IMPORTANT]
> A partir de 1 de outubro de 2019, Microsoft StaffHub será desativada. Estamos compilando StaffHub recursos, incluindo gerenciamento de agenda e tarefa, em Microsoft Teams. Recursos adicionais para os trabalhadores firstline serão distribuir às equipes ao longo do tempo. Para saber mais, consulte [Microsoft StaffHub para ser retirado](microsoft-staffhub-to-be-retired.md).  

## <a name="overview-of-shifts"></a>Visão geral das mudanças
O aplicativo desloca no Microsoft Teams mantém firstline trabalhadores conectados e em sincronia. Ele é criado móvel primeiro para comunicação para equipes e gerenciamento de tempo rápida e eficaz. Desloca permite que trabalhadores firstline e seus gerentes usam seus dispositivos móveis para gerenciar agendas e manter contato. 

- Gerentes de criar, atualizar e gerenciar agendas shift para equipes. Eles podem enviar mensagens para uma pessoa ("há um excesso na base") ou a toda a equipe ("o GM regional está sendo recebido em 20 minutos"). Eles também podem enviar documentos de diretivas, boletins de notícias e vídeos. 
- Funcionários exibir suas mudanças futuras, podem ver quem mais está agendado para o dia, solicitar trocar ou oferecer um turno e tempo de solicitação. 

É importante saber que desloca atualmente não dá suporte aos usuários convidados. Isso significa que convidados em uma equipe não podem ser adicionados a ou usam agendas shift quando acesso como convidado está ativado em equipes. 

## <a name="availability-of-shifts"></a>Disponibilidade do desloca

Desloca está disponível em todas as assinaturas do Office 365 que incluem equipes, com algumas exceções. As exceções são conosco governamentais nuvem da comunidade (GCC) e equipes livres. Desloca não está disponível no Office 365 conosco agências governamentais ou equipes livre ofertas.

Para saber mais sobre o licenciamento para equipes, incluindo uma lista de assinaturas do Office 365 que inclui as equipes, consulte [Licenciamento do Office 365 para equipes](../Office-365-licensing.md).

## <a name="location-of-shifts-data"></a>Localização dos dados desloca

Atualmente, os dados de desloca são armazenados no Windows Azure em centros de dados na América do Norte, Europa Ocidental e Pacífico Asiático. Para obter mais informações sobre onde os dados são armazenados, consulte [onde estão meus dados](http://o365datacentermap.azurewebsites.net/)?

## <a name="set-up-shifts"></a>Configurar desloca

### <a name="enable-or-disable-shifts-in-your-organization"></a>Habilitar ou desabilitar desloca em sua organização

Desloca é habilitado por padrão para todos os usuários de equipes em sua organização. Você pode desativar ou ativar o aplicativo para sua organização no Centro de administração do Microsoft 365.

1. Entrar no Centro de administração do Microsoft 365 com sua conta de administração do Office 365.
2. Vá para **configurações** > **Serviços & complementos** > **Equipes da Microsoft**. 
3. Em **configurações de todo o locatário**, selecione **aplicativos**e em **Aplicativos padrão**, desmarque ou marque a caixa de seleção **desloca** para desativar ou ativar o aplicativo. 

    ![Captura de tela da seção aplicativos padrão] (../media/firstline-worker-enable-disable-shifts.png "Captura de tela da seção padrão Apps no Centro de administração do Microsoft 365, mostrando a lista de aplicativos, incluindo o aplicativo desloca")

### <a name="use-the-firstlineworker-app-setup-policy-to-pin-shifts-to-teams"></a>Usar a diretiva de instalação de app FirstLineWorker para muda de pin para equipes

> [!INCLUDE [Preview customer token](../includes/preview-feature.md)]

Políticas de configuração de aplicativo permitem que você personalize equipes para destacar os aplicativos que são mais importantes para os usuários em sua organização. Os aplicativos definidos em uma política estão vinculados à barra de aplicativos&mdash;barra no lado do cliente de desktop do equipes e na parte inferior dos clientes móveis equipes&mdash;onde os usuários possam rapidez e facilidade acessá-los. 
 
As equipes inclui uma diretiva de instalação de aplicativo FirstLineWorker interna que você pode atribuir aos trabalhadores firstline em sua organização. Por padrão, a política inclui os aplicativos de atividade, desloca, Chat e chamada. 

Para exibir a política de FirstLineWorker, no painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes app** > **políticas de configuração de aplicativo**.

![Captura de tela da política de instalação de aplicativo FirstLineWorker no Centro de administração de equipes da Microsoft] (../media/firstline-worker-app-setup-policy.png "Captura de tela da política de instalação de aplicativo FirstLineWorker no Centro de administração de equipes da Microsoft")

#### <a name="assign-the-firstlineworker-policy-to-individual-users"></a>Atribuir a política de FirstLineWorker a usuários individuais

1. No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.
2. Ao lado de **políticas atribuído**, escolha **Editar**.
3. Em **política de instalação do aplicativo de equipes**, selecione **FirstLineWorker**e, em seguida, escolha **Salvar**.

#### <a name="assign-the-firstlineworker-app-setup-policy-to-users-in-a-group"></a>Atribuir a diretiva de instalação de aplicativo FirstLineWorker aos usuários em um grupo

Você pode atribuir a diretiva de instalação de aplicativo FirstLineWorker aos usuários em um grupo, como um grupo de segurança, estabelecendo conexão com o Azure Active Directory PowerShell para o módulo de gráfico e do Skype para o módulo de PowerShell de negócios. Para obter mais informações sobre como usar o PowerShell para gerenciar equipes, consulte [Visão geral do PowerShell equipes](../teams-powershell-overview.md).

Neste exemplo, atribuímos a diretiva de instalação de aplicativo FirstLineWorker a todos os usuários no grupo Firstline equipe da Contoso.

> [!NOTE]
> Certificar-se de que você primeiro conecte-se para o Windows Azure Active Directory PowerShell para o módulo de gráfico e Skype para o módulo de PowerShell de negócios seguindo as etapas em [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).

Obtenha o GroupObjectId do grupo específico.
```
$group = Get-AzureADGroup -SearchString "Contoso Firstline Team"
```
Obtenha os membros do grupo especificado.
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
Atribua a todos os usuários no grupo à diretiva de instalação do aplicativo FirstLineWorker.
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "FirstLineWorker" -Identity $_.EmailAddress}
``` 
Dependendo do número de membros no grupo, este comando pode levar alguns minutos para executar.

## <a name="related-topics"></a>Tópicos relacionados
- [Desloca ajuda para trabalhadores de firstline e gerentes](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)
