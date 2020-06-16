---
title: Configurando as várias políticas
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8270452893e6e2e531eed86d730a1ea4f9f604fc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>Configurando as várias políticas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>Configurando as várias políticas

Aqui estão as várias políticas que você pode configurar na sua topologia do Lync Server 2013, antes de executar a ferramenta de estresse e desempenho do Lync Server 2013.

<div>

## <a name="configuring-the-archiving-policy"></a>Configurando a política de arquivamento

Consulte o exemplo de script ArchivingPolicy.ps1. Você só precisará usar esse script se um servidor de arquivamento estiver implantado em sua topologia. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets de arquivamento e monitoramento no Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>Configurando a política de conferência

Consulte o exemplo de script MeetingPolicy.ps1. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets da webconferência no Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>Configurando a política de contatos

Confira o exemplo ContactsPolicy.ps1. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets de presença e im no Lync server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-federation-policy"></a>Configurando a política de Federação

Confira o exemplo FederationPolicy.ps1. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets do servidor de borda no Lync server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) e [cmdlets de acesso externo e de Federação no Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>Configurando a política de controle de admissão de chamadas

Confira o exemplo BandwidthPolicy.ps1. Para obter detalhes, consulte o artigo [visão geral da documentação do Lync server 2013 do controle de admissão de chamadas no Lync server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) e a ajuda do cmdlet para os [cmdlets do controle de admissão de chamadas no Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>Configurando as regras de roteamento de voz

Confira o exemplo RoutingRules.ps1. Ao configurar as regras de roteamento de voz, anote o contexto de telefone (ou seja,/Location perfil ou/SimpleName) e códigos de área interna/externa para que você possa especificá-los ao criar usuários e durante a configuração do LyncPerfTool (especificamente para PSTN-UC e UC-PSTN). Por exemplo, o parâmetro SimpleName na chamada para o cmdlet **New-CsDialPlan** no exemplo RoutingRules.ps1 deve ser usado para o valor LocationProfile na seguinte figura de UserProfileGenerator.exe.

![Exemplo de regra de roteamento de voz.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Exemplo de regra de roteamento de voz.")

Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets do Enterprise Voice no Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>Configurando aplicativo de atendedor de conferência

Confira o exemplo ConferenceAutoAttendantConfiguration.ps1. Anote o número de telefone do ConferencingAutoAttendant (1121111111, por padrão), para que você possa digitá-lo na ferramenta de configuração da ferramenta LyncPerf para geração de configuração.

![Configurando o aplicativo de atendedor de conferência](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configurando o aplicativo de atendedor de conferência")

Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets da webconferência no Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) e [cmdlets de conferência discada no Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Configurando o serviço de estacionamento de chamada do Lync Server

O estacionamento de chamadas está desabilitado por padrão. Confira o exemplo CallParkConfiguration.ps1. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets do aplicativo de estacionamento de chamada no Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-emergency-calls"></a>Configurando chamadas de emergência

Execute as seguintes etapas para configurar o estresse e o teste de desempenho para chamadas de emergência.

1.  Configurar uma rota de voz para chamadas de emergência. Consulte o RoutingRules.ps1 script no comentário "Route E911 to PSTN" para obter um exemplo de como configurar essa rota de voz.
    
    <div>
    

    > [!WARNING]  
    > O comando de exemplo em RoutingRules.ps1 tem um padrão de número que inclui o número 119 em vez de 911. Você deve evitar o uso de 911 (ou seu número de emergência local real) para evitar chamadas acidentais para seus operadores de emergência locais durante o teste de carga. Essa configuração é apenas para fins de simulação.

    
    </div>

2.  Configure endereços preenchendo os valores na guia **Lis** no UserProvisioningTool, conforme mostrado na figura a seguir.
    
    ![Configurando o serviço de informações de local.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configurando o serviço de informações de local.")  

3.  Clique em **gerar arquivos de configuração de Lis**.

4.  Arquivos CSV para portas, sub-redes, comutadores e pontos de acesso sem fio (WAPs) e um arquivo XML para a ferramenta de estresse e desempenho do Lync Server 2013, são gerados. Os arquivos CSV devem ser usados como entradas (na mesma pasta) ao configurar o serviço de informações de local (LIS) com o script LisConfiguration.ps1. Mova o arquivo Locations0.xml gerado para a mesma pasta que o executável da ferramenta de sobrecarga e desempenho (LyncPerfTool.exe) do Lync Server 2013, que executará os cenários de perfil de local (plano de discagem).

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>Criar, habilitar, configurar e desabilitar usuários

Você deve criar todos os seus usuários antes de executar os scripts a seguir. Siga as instruções em [criar usuários e contatos](create-users-and-contacts.md) para criar usuários. Para obter detalhes, consulte a documentação do cmdlet do Lync Server 2013 para os cmdlets [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))e [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) .

</div>

<div>

## <a name="configuring-response-group-application"></a>Configurando o aplicativo de grupo de resposta

Confira o exemplo ResponseGroupConfiguration.ps1. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets do aplicativo grupo de resposta no Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)). Para revisar a configuração do aplicativo grupo de resposta, consulte `https://<poolfqdn>/RgsConfig/` , conforme mostrado na figura a seguir.

![A ferramenta de configuração do grupo de resposta.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "A ferramenta de configuração do grupo de resposta.")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

