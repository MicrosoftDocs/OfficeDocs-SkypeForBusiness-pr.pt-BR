---
title: Configurando as várias políticas
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6316a1027de963cefea6c0c76051f09cb5d33538
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727681"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a>Configurando as várias políticas

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-24_

<div>

## <a name="configuring-the-various-policies"></a>Configurando as várias políticas

Aqui estão as várias políticas que você pode configurar na sua topologia do Lync Server 2013, antes de executar a ferramenta de stress e desempenho do Lync Server 2013.

<div>

## <a name="configuring-the-archiving-policy"></a>Configurar a política de arquivamento

Consulte o script de exemplo ArchivingPolicy. ps1. Você só precisará usar esse script se um servidor de arquivamento estiver implantado na sua topologia. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para [arquivamento e monitoramento de cmdlets no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a>Configurar a política de conferência

Consulte o script de exemplo MeetingPolicy. ps1. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para [cmdlets de Webconferência no Lync server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-contacts-policy"></a>Configurando a política de contatos

Consulte o exemplo ContactsPolicy. ps1. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets de presença e mensagens instantâneas no Lync server 2013](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-federation-policy"></a>Configurando a política de Federação

Consulte o exemplo FederationPolicy. ps1. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para [cmdlets do servidor de borda no Lync server 2013](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) e [cmdlets de acesso externo e Federação no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a>Configurando a política de controle de admissão de chamadas

Consulte o exemplo BandwidthPolicy. ps1. Para obter detalhes, consulte a [visão geral da documentação do Lync Server 2013 do controle de admissão de chamadas no Lync server 2013](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) e a ajuda do cmdlet para [cmdlets de controle de admissão de chamadas no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a>Configurando as regras de roteamento de voz

Consulte o exemplo RoutingRules. ps1. Ao configurar as regras de roteamento de voz, anote o contexto do telefone (ou seja, o perfil do/Location ou/SimpleName) e os códigos de área interna/externa para que você possa especificá-los ao criar usuários e durante a configuração do LyncPerfTool (especificamente para PSTN-UC e UC-PSTN). Por exemplo, o parâmetro SimpleName na chamada para o cmdlet **New-CsDialPlan** no exemplo RoutingRules. ps1 deve ser usado para o valor LocationProfile na seguinte imagem do UserProfileGenerator. exe.

![Regra de roteamento de voz de exemplo.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Regra de roteamento de voz de exemplo.")

Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para [cmdlets do Enterprise Voice no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a>Configurando o aplicativo de assistente de conferência

Consulte o exemplo ConferenceAutoAttendantConfiguration. ps1. Anote o número de telefone ConferencingAutoAttendant (1121111111, por padrão), para que você possa digitá-lo na ferramenta de configuração da ferramenta LyncPerf para geração de configuração.

![Configurando o aplicativo assistente de conferência](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configurando o aplicativo assistente de conferência")

Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para [cmdlets de Webconferência no Lync server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) e [cmdlets de conferência discada no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a>Configurando o serviço de estacionamento de chamadas do Lync Server

O parque de chamadas está desabilitado por padrão. Consulte o exemplo CallParkConfiguration. ps1. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets do aplicativo de estacionamento de chamada no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\)).

</div>

<div>

## <a name="configuring-emergency-calls"></a>Configurando chamadas de emergência

Execute as etapas a seguir para configurar o teste de stress e desempenho para chamadas de emergência.

1.  Configurar uma rota de voz para chamadas de emergência. Consulte o script RoutingRules. ps1 sob o comentário "Route E911 to PSTN" para obter um exemplo de como configurar essa rota de voz.
    
    <div>
    

    > [!WARNING]  
    > O comando de exemplo em RoutingRules. ps1 tem um padrão de número que inclui o número 119 em vez de 911. Evite usar o 911 (ou o seu número de emergência local real) para evitar chamadas acidentais para seus operadores de emergência locais durante o teste de carga. Essa configuração é somente para fins de simulação.

    
    </div>

2.  Para configurar endereços, preencha os valores na guia **Lis** no UserProvisioningTool, conforme mostrado na figura a seguir.
    
    ![Configurar o serviço de informações de localização.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configurar o serviço de informações de localização.")  

3.  Clique em **gerar arquivos Lis config**.

4.  Arquivos CSV para portas, sub-redes, opções e pontos de acesso sem fio (WAPs) e um arquivo XML para a ferramenta de stress e desempenho do Lync Server 2013 são gerados. Os arquivos CSV devem ser usados como entradas (na mesma pasta) durante a configuração do LIS (serviço de informações de localização) com o script LisConfiguration. ps1. Mova o arquivo Locations0. XML gerado para a mesma pasta que o executável da ferramenta de desempenho e sobrecarga do Lync Server 2013 (LyncPerfTool. exe), que executará cenários de perfil de localização (plano de discagem).

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a>Criando, habilitando, Configurando e desabilitando usuários

Você deve criar todos os usuários antes de executar os scripts a seguir. Siga as instruções em [criar usuários e contatos](create-users-and-contacts.md) para criar usuários. Para obter detalhes, consulte a documentação do cmdlet do Lync Server 2013 para os cmdlets [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [set-CsUser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))e [Disable-CsUser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) .

</div>

<div>

## <a name="configuring-response-group-application"></a>Configurando o aplicativo grupo de resposta

Consulte o exemplo ResponseGroupConfiguration. ps1. Para obter detalhes, consulte a documentação do Lync Server 2013 e a ajuda do cmdlet para os [cmdlets do aplicativo grupo de resposta no Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\)). Para revisar a configuração do aplicativo grupo `https://<poolfqdn>/RgsConfig/`de resposta, consulte, conforme mostrado na figura a seguir.

![A ferramenta de configuração de grupo de resposta.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "A ferramenta de configuração de grupo de resposta.")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

