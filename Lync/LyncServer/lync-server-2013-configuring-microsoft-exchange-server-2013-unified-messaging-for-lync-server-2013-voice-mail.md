---
title: 'Lync Server 2013: Configurando a Unificação de mensagens do Microsoft Exchange Server 2013 para Lync Server 2013 caixa postal'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Exchange Server 2013 Unified Messaging for Lync Server 2013 voice mail
ms:assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687983(v=OCS.15)
ms:contentKeyID: 49733573
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7376ce3cbafe1321878a28e43e9bc3ab065c990f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525929"
---
# <a name="configuring-microsoft-exchange-server-2013-unified-messaging-for-microsoft-lync-server-2013-voice-mail"></a>Configurando a Unificação de mensagens do Microsoft Exchange Server 2013 para o Microsoft Lync Server 2013 voice mail

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-04_

O Microsoft Lync Server 2013 permite que você tenha mensagens de caixa postal armazenadas no Microsoft Exchange Server 2013; essas mensagens de voz serão exibidas como mensagens de email nas caixas de entrada dos seus usuários. Esse recurso também foi encontrado nas edições 2010 do Lync Server e no Exchange; no entanto, o processo de configuração dessa "Unificação de mensagens" foi simplificado nas edições 2013 graças à introdução do componente roteador de chamadas de UM. Esse componente é instalado no servidor de acesso para cliente do Exchange 2013, e todas as chamadas para a Unificação de mensagens do Exchange (como uma caixa postal) são roteadas primeiro pelo roteador de chamada e, em seguida, são redirecionadas para o servidor de caixa de correio apropriado.

Se você já configurou a autenticação de servidor para servidor entre o Lync Server 2013 e o Exchange 2013, você está pronto para configurar a Unificação de mensagens. Para fazer isso, você deve primeiro criar e atribuir um novo plano de discagem de Unificação de mensagens no seu servidor Exchange. Por exemplo, esses dois comandos (executados de dentro do Shell de gerenciamento do Exchange) configuram um novo plano de discagem de 3 dígitos para o Exchange:

    New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
    Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"

O primeiro comando no exemplo, o parâmetro VoIPSecurity e o valor de parâmetro "Secured" indica que o canal de sinalização é criptografado usando TLS. O URIType "SipName" indica que as mensagens serão enviadas e recebidas usando o protocolo SIP e o CountryOrRegionCode de 1 indica que o plano de discagem se aplica aos EUA.

No segundo comando, o valor do parâmetro para o parâmetro ConfiguredInCountryOrRegionGroups especifica os grupos no país que podem ser usados com este plano de discagem. O valor do parâmetro "Anywhere \* , \* \* ", "define o seguinte:

  - Nome do grupo ("Anywhere")

  - AllowedNumberString ( \* , um caractere curinga indicando que qualquer sequência numérica é permitida)

  - DialNumberString ( \* , um caractere curinga indicando que qualquer número discado é permitido)

  - Textcomment ( \* , um caractere curinga indicando que qualquer comando de texto é permitido)

<div>


> [!NOTE]  
> Criar um novo plano de discagem também criará uma política de caixa de correio padrão.



</div>

Após criar e configurar o novo plano de discagem, você deve adicionar o novo plano de discagem ao seu servidor do unified messaging e modificar o modo de inicialização do servidor; em particular, você deve definir o modo de inicialização para "Dual". Você pode executar essas duas tarefas de dentro do Shell de gerenciamento do Exchange:

    Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"

Após a configuração do servidor de Unificação de mensagens, você deve executar o cmdlet Enable-ExchangeCertificate para garantir que seu certificado do Exchange seja aplicado ao serviço de Unificação de mensagens:

    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"

Após o certificado ter sido atribuído corretamente, você deve parar e reiniciar o serviço MsExchangeUM no servidor do unified messaging. Este serviço deve ser parado e reiniciado a qualquer momento que você alterar o modo de inicialização.

Após finalizar a configuração do servidor do unified messaging, é possível configurar o Roteador de Chamada UM:

    Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
    Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"

Como o modo de inicialização foi alterado, você deve parar e reiniciar o serviço do MsExchangeUMCR no computador hospedando o Roteador de Chamada UM.

Para concluir a configuração do unified messaging, você precisa criar uma política de caixa de correio do UM e usar essa política para habilitar os usuários para o unified messaging. É possível criar uma política de caixa de correio usando um comando semelhante ao seguinte:

    New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"

E é possível habilitar um usuário para unified messaging utilizando um comando semelhante ao seguinte:

    Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"

No comando anterior, o parâmetro Extensions representa o número de extensão telefônica do usuário. Neste exemplo, o usuário possui o número de extensão 100.

Após habilitar esta caixa de correio, o usuário kenmyer@litwareinc.com deve poder usar o Exchange unified messaging. Você pode verificar se o usuário pode se conectar ao UM do Exchange executando o cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMConnectivity) a partir do Shell de gerenciamento do Lync Server:

    $credential = Get-Credential "litwareinc\kenmyer"
    
    Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential

Se você possui um segundo usuário habilitado para unified messaging, é possível usar o cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/Test-CsExUMVoiceMail) para verificar se este segundo usuário pode deixar uma mensagem de caixa postal para o primeiro usuário.

    $credential = Get-Credential "litwareinc\pilar"
    
    Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential

</div>

<span> </span>

</div>

</div>

</div>

