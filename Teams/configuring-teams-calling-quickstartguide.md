---
title: "Guia de Início Rápido - Como configurar Planos de Chamadas no Microsoft Teams"
author: arachmanGitHub
ms.author: MyAdvisor
manager: serdars
ms.date: 12/12/2017
ms.topic: article
ms.service: msteams
ms.reviewer: MyAdvisor, lolaj
description: "Guia de Início Rápido para configurar Planos de Chamadas no Microsoft Teams."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6a32b615905d39bf8b91688f461f804a28d5a52d
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2018
---
<a name="quick-start-guide-configuring-calling-plans-in-microsoft-teams"></a>Guia de Início Rápido: como configurar Planos de Chamadas no Microsoft Teams
==============================================================

Este guia o ajudará a estabelecer um grupo de usuários para que eles possam explorar os Planos de Chamadas no Microsoft Teams.

Leia o anúncio feito em 12 de dezembro de 2017, dos Planos de Chamadas no Microsoft Teams: [A comunicação inteligente avança com as chamadas do Microsoft Teams](https://aka.ms/ipyqus)

> [!NOTE]
> Recomendamos que, em paralelo com este Guia de Início Rápido, você use as [orientações prática](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans) e o [FastTrack](https://aka.ms/cloudvoice) para planejar e realizar uma distribuição bem-sucedida.

Com a inclusão dos Planos de Chamadas, um recurso do Office 365 acionado pelo Skype for Business, agora você pode usar o Microsoft Teams para fazer e receber chamadas de telefones fixos e celulares pela PSTN (Rede Telefônica Pública Comutada).

![Fazendo chamadas no Microsoft Teams](media/Calling_in_Teams.png)

## <a name="prerequisites-for-enabling-the-calls-tab-in-teams"></a>Pré-requisitos para habilitar a guia **Chamadas** no Microsoft Teams
Para habilitar a guia **Chamadas** no Microsoft Teams e permitir que os usuários façam e recebam chamadas PSTN, será necessário provisionar os usuários para o Sistema de Telefonia e os Planos de Chamadas. Para saber como configurar isso, leia [Configurar Planos de Chamadas](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0).

> [!IMPORTANT]
> Antes de configurar os Planos de Chamadas no Microsoft Teams, esteja ciente das seguintes limitações:
> * **O Microsoft Teams não dá suporte ao Hybrid Voice** - o Hybrid Voice ainda não é compatível com o Microsoft Teams. Recomendamos que os clientes do Hybrid Voice não alterem nenhuma das políticas para receber chamadas no Microsoft Teams, pois isso causaria interrupções do serviço.
> * **O Microsoft Teams não dá suporte a chamadas federadas** - as chamadas federadas (chamadas entre locatários/empresas) ainda não são compatíveis com o Microsoft Teams. As chamadas federadas serão encaminhadas para o Skype for Business, independentemente da configuração das chamadas, até que o Microsoft Teams ofereça suporte a elas.

## <a name="teams-interop-policy-configuration"></a>Configuração da política de interoperabilidade do Microsoft Teams
Para habilitar o Microsoft Teams para receber chamadas, é necessário atualizar a política de interoperabilidade do Microsoft Teams usando uma sessão do Windows PowerShell remoto com os cmdlets [`*-CsTeamsInteropPolicy`](https://docs.microsoft.com/powershell/module/skype) do Skype for Business para redirecionar as chamadas para o Microsoft Teams. Para obter mais informações sobre a política de interoperabilidade do Microsoft Teams, veja [Interoperabilidade entre o Microsoft Teams e o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability).

> [!TIP]
> Para encontrar os cmdlets do PowerShell necessários, digite "CsTeamsInteropPolicy" na caixa **Filtrar** na [documentação de cmdlets do PowerShell para o Skype for Business](https://docs.microsoft.com/powershell/module/skype).

### <a name="default-teams-interop-policy"></a>Política de interoperabilidade padrão do Microsoft Teams
O Microsoft Teams tem uma configuração de política padrão criada para garantir que os fluxos de trabalho de negócios existentes não sejam interrompidos durante a implantação do Microsoft Teams. Por padrão, as chamadas VoIP, PSTN e federadas para seus usuários continuarão sendo encaminhadas para o Skype for Business até que você atualize a política para habilitar as chamadas de entrada para o Microsoft Teams. Isso garante que não haja interrupções involuntárias nos serviços de voz quando você começa a testar e implantar o Microsoft Teams.

A política de interoperabilidade do Microsoft Teams tem a seguinte configuração padrão:

    Identity                   : Global
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Por padrão, o comportamento da configuração padrão inclui:
* **Para os clientes existentes do Skype for Business**, esta política tem como objetivo garantir que as chamadas do Skype for Business sejam direcionadas para o Skype for Business, e as chamadas do Microsoft Teams sejam direcionadas para o Microsoft Teams. As chamadas PSTN e federadas serão direcionadas para o Skype for Business quando essa política estiver em vigor.
* **Para os clientes que não têm o Skype for Business**, quando em vigor, além das chamadas entre usuários do Microsoft Teams, somente as chamadas PSTN de saída estarão disponíveis no Microsoft Teams. Para receber chamadas PSTN no Microsoft Teams, será necessário alterar a política de interoperabilidade do Microsoft Teams atribuída a seus usuários.

> [!NOTE]
> A guia Chamadas estará habilitada no Microsoft Teams para os usuários que foram provisionados com licenças do Sistema de Telefonia e de Planos de Chamadas para uso com o Skype for Business Online e que têm configurada a política de interoperabilidade global padrão do Microsoft Teams, e eles poderão fazer chamadas PSTN de saída no Microsoft Teams sem a necessidade de qualquer ação por parte dos administradores.

#### <a name="how-to-configure-teams-to-use-the-default-policy"></a>Como configurar o Microsoft Teams para usar a política padrão
Por padrão, a política de interoperabilidade global do Microsoft Teams é aplicada a todos os usuários em seu locatário, sendo definida com as configurações padrão, conforme descrito acima. Se, por algum motivo, você atribuiu políticas diferentes a seus usuários e deseja reverter para a configuração padrão, deve aplicar a política de interoperabilidade global do Microsoft Teams via sessão do Windows PowerShell remoto do Skype for Business:

    Grant-CsTeamsInteropPolicy -PolicyName Global -Identity user@contoso.com

> [!WARNING]
> Embora seja possível modificar a política de interoperabilidade global do Microsoft Teams a partir dos valores padrão, não é recomendável fazer isso. 

## <a name="configuring-teams-to-receive-inbound-pstn-calls"></a>Configuração do Microsoft Teams para receber chamadas PSTN de entrada
Para receber chamadas PSTN de entrada no Microsoft Teams, é necessário configurar o Microsoft Teams como aplicativo de chamadas padrão, aplicando a política de interoperabilidade do Microsoft Teams com o parâmetro `CallingDefaultClient` definido para o Teams.

> [!IMPORTANT]
> Recomendamos aplicar essa configuração a um conjunto inicial de usuários para explorar as incríveis novas funcionalidades de chamadas do Microsoft Teams antes de fazer alterações mais abrangentes ou em toda a organização.

Pense na possibilidade de usar a seguinte política de interoperabilidade do Microsoft Teams pré-configurada para encaminhar as chamadas PSTN de entrada para o Microsoft Teams:

    Identity                   : Tag:DisallowOverrideCallingTeamsChatTeams
    AllowEndUserClientOverride : False
    CallingDefaultClient       : Teams
    ChatDefaultClient          : Teams

O comportamento da política acima inclui:
* **Para os clientes existentes do Skype for Business**, esta política tem como objetivo redirecionar as chamadas de entrada para o Microsoft Teams. Isso inclui chamadas VoIP (do Microsoft Teams e do Skype for Business) e PSTN. As chamadas federadas continuarão sendo recebidas no Skype for Business. 
* **Para os clientes que não têm o Skype for Business**, quando em vigor, as chamadas PSTN serão recebidas no Microsoft Teams. Por enquanto, as chamadas federadas **não têm suporte** no Microsoft Teams.

> [!WARNING]
> No momento, a alteração de `CallingDefaultClient` para o Microsoft Teams também afeta as chamadas para telefones IP do Skype for Business. As chamadas de entrada não serão recebidas em telefones e vão tocar somente nos clientes do Microsoft Teams. Consulte o [Skype for Business to Microsoft Teams Capabilities Roadmap](https://aka.ms/skype2teamsroadmap) para obter informações sobre o suporte para telefones SIP certificados existentes.

### <a name="how-to-configure-teams-to-receive-pstn-calls"></a>Como configurar o Microsoft Teams para receber chamadas PSTN
Aplique a política de interoperabilidade do Microsoft Teams, conforme descrito acima, via sessão do Windows PowerShell remoto do Skype for Business para redirecionar as chamadas para o Microsoft Teams:

    Grant-CsTeamsInteropPolicy -PolicyName tag:DisallowOverrideCallingTeamsChatTeams -Identity user@contoso.com

## <a name="configuring-teams-to-allow-users-to-change-their-preferred-calling-experience"></a>Configuração do Microsoft Teams para permitir que os usuários alterem sua experiência de chamadas preferencial
Para que os usuários possam decidir sobre sua experiência de chamadas preferencial, seja para receber chamadas no Microsoft Teams ou no Skype for Business, você precisa criar uma política de interoperabilidade personalizada do Microsoft Teams que habilite o parâmetro `AllowEndUserClientOverride`.

Veja a seguir um exemplo da política de interoperabilidade do Microsoft Teams para habilitar a opção do usuário de experiência de chamadas preferencial:

    Identity                   : Tag:CustomPolicy
    AllowEndUserClientOverride : True
    CallingDefaultClient       : Default
    ChatDefaultClient          : Default

Quando essa política personalizada for aplicada para os usuários, a opção de alterar o aplicativo de chamadas preferencial estará disponível no cliente do Microsoft Teams para que os próprios usuários façam suas alterações.

![Opção preferencial de aplicativo de chamadas](media/Preferred_calling_application_option.png)

> [!IMPORTANT]
> Recomendamos aplicar essa configuração a um conjunto inicial de usuários antes de fazer alterações mais abrangentes ou em toda a organização.

### <a name="how-to-create-and-apply-the-custom-teams-interop-policy"></a>Como criar e aplicar a política de interoperabilidade personalizada do Microsoft Teams
Para criar a política de interoperabilidade personalizada do Microsoft Teams, conforme descrito acima, via sessão do Windows PowerShell remoto do Skype for Business, faça o seguinte:

    New-CsTeamsInteropPolicy -Identity tag:CustomPolicy -AllowEndUserClientOverride:$True -CallingDefaultClient:Default -ChatDefaultClient:Default

    Grant-CsTeamsInteropPolicy -PolicyName tag:CustomPolicy -Identity user@contoso.com



## <a name="see-also"></a>Consulte também
[Configurar Planos de Chamadas](https://support.office.com/article/Set-up-Calling-Plans-57893158-1acd-44ac-acaf-19f58264a9e0)

[Interoperabilidade entre o Microsoft Teams e o Skype for Business](https://docs.microsoft.com/MicrosoftTeams/teams-and-skypeforbusiness-interoperability)

[Orientações práticas para Sistema de Telefonia com Planos de Chamadas no Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/phone-system-with-calling-plans)

[Referência de cmdlets do PowerShell para o Skype for Business](https://docs.microsoft.com/powershell/module/skype)

[Referência de cmdlets do PowerShell para o Microsoft Teams](https://docs.microsoft.com/powershell/module/teams)
