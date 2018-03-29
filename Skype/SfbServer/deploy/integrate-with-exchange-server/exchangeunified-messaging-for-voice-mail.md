---
title: Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/19/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1be9c4f4-fd8e-4d64-9798-f8737b12e2ab
description: 'Resumo: Configure o Unificação de mensagens do Exchange Server para Skype para caixa postal Business Server.'
ms.openlocfilehash: 9f4cb3dcd43d8f6300a5fbe38bd37c40d48e8273
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-exchange-server-unified-messaging-for-skype-for-business-server-2015-voice-mail"></a>Configurar a Unificação de Mensagens do Exchange Server para a caixa postal do Skype for Business Server 2015
 
**Resumo:** Configure Unificação de mensagens do Exchange Server do Skype para caixa postal Business Server.
  
Skype para Business Server 2015 permite que você tenha mensagens da caixa postal armazenadas no Exchange Server 2016 ou Exchange Server 2013; Essas mensagens de caixa postal aparecerão como mensagens de email nas caixas de entrada dos usuários. 
  
Se você já tiver configurado a autenticação de servidor-para-servidor entre o Skype para Business Server 2015 e Exchange Server 2016 ou Exchange Server 2013, em seguida, você estará pronto para configurar a Unificação de mensagens. Para fazer isso, você deve primeiro criar e atribuir um novo plano de discagem mensagens unificadas em seu servidor Exchange. Por exemplo, estes dois comandos (executados de dentro do Shell de gerenciamento do Exchange) configurar um novo plano de discagem de 3 dígitos para o Exchange:
  
```
New-UMDialPlan -Name "RedmondDialPlan" -VoIPSecurity "Secured" -NumberOfDigitsInExtension 3 -URIType "SipName" -CountryOrRegionCode 1
Set-UMDialPlan "RedmondDialPlan" -ConfiguredInCountryOrRegionGroups "Anywhere,*,*,*" -AllowedInCountryOrRegionGroups "Anywhere"
```

O primeiro comando no exemplo, o parâmetro VoIPSecurity e o valor de parâmetro "Secured" indica que o canal de sinalização é criptografado usando TLS. O URIType "SipName" indica que as mensagens serão enviadas e recebidas usando o protocolo SIP e o CountryOrRegionCode de 1 indica que o plano de discagem se aplica aos EUA.
  
No segundo comando, o valor do parâmetro para o parâmetro ConfiguredInCountryOrRegionGroups especifica os grupos no país que podem ser usados com este plano de discagem. O valor do parâmetro "em qualquer lugar,\*,\*,\*" define o seguinte:
  
- Nome do grupo ("Anywhere")
    
- AllowedNumberString (\*, um caractere curinga indicando que qualquer sequência numérica é permitida)
    
- DialNumberString (\*, um caractere curinga indicando que qualquer número discado é permitido)
    
- TextComment (\*, um caractere curinga indicando que qualquer comando de texto é permitido)
    
> [!NOTE]
> Criar um novo plano de discagem também criará uma Política de Caixa de Correio Padrão. 
  
Após criar e configurar o novo plano de discagem, você deve adicionar esse plano ao seu servidor do unificação de mensagens e modificar o modo de inicialização do servidor; em particular, você deve definir o modo de inicialização para "Dual". Você pode executar essas tarefas de dentro do Shell de gerenciamento do Exchange:
  
```
Set-UmService -Identity "atl-exchangeum-001.litwareinc.com" -DialPlans "RedmondDialPlan" -UMStartupMode "Dual"
```

Após o servidor do unified messaging ter sido configurado, você Avançar deve executar o cmdlet Enable-ExchangeCertificate para garantir que o seu certificado do Exchange é aplicado ao serviço do unified messaging:
  
```
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "EA5A332496CC05DA69B75B66111C0F78A110D22d" -Services "SMTP","IIS","UM"
```

Após o certificado ter sido atribuído corretamente, você deve parar e reiniciar o serviço MsExchangeUM no servidor do unified messaging. Este serviço deve ser parado e reiniciado a qualquer momento que você alterar o modo de inicialização.
  
Após finalizar a configuração do servidor do unified messaging, é possível configurar o Roteador de Chamada UM:
  
```
Set-UMCallRouterSettings -Server "atl-exchange-001.litwareinc.com" -UMStartupMode "Dual" -DialPlans "RedmondDialPlan" 
Enable-ExchangeCertificate -Server "atl-umserver-001.litwareinc.com" -Thumbprint "45BAA32496CC891169B75B9811320F78A1075DDA" -Services "IIS","UMCallRouter"
```

Como o modo de inicialização foi alterado, você deve parar e reiniciar o serviço do MsExchangeUMCR no computador hospedando o Roteador de Chamada UM.
  
Para concluir a configuração do unified messaging, você precisa criar uma política de caixa de correio do UM e usar essa política para habilitar os usuários para o unified messaging. É possível criar uma política de caixa de correio usando um comando semelhante ao seguinte:
  
```
New-UMMailboxPolicy -Name "RedmondMailboxPolicy" -AllowedInCountryOrRegionGroups "Anywhere"
```

E é possível habilitar um usuário para unified messaging utilizando um comando semelhante ao seguinte:
  
```
Enable-UMMailbox -Extensions 100 -SIPResourceIdentifier "kenmyer@litwareinc.com" -Identity "litwareinc\kenmyer" -UMMailboxPolicy "RedmondMailboxPolicy"
```

No comando anterior, o parâmetro Extensions representa o número de extensão telefônica do usuário. Neste exemplo, o usuário possui o número de extensão 100.
  
Após habilitar esta caixa de correio, o usuário kenmyer@litwareinc.com poderá usar a unificação de mensagens do Exchange. Você pode verificar se o usuário pode se conectar a UM do Exchange executando o cmdlet [Test-CsExUMConnectivity](https://docs.microsoft.com/powershell/module/skype/test-csexumconnectivity?view=skype-ps) do dentro do Skype do Shell de gerenciamento do servidor de negócios:
  
```
$credential = Get-Credential "litwareinc\kenmyer"

Test-CsExUMConnectivity -TargetFqdn "atl-cs-001.litwareinc.com" -UserSipAddress "sip:kenmyer@litwareinc.com" -UserCredential $credential
```

Se você tiver um segundo usuário que tenha sido habilitado para Unificação de mensagens, você pode usar o cmdlet [Test-CsExUMVoiceMail](https://docs.microsoft.com/powershell/module/skype/test-csexumvoicemail?view=skype-ps) para verificar se o segundo usuário pode deixar uma mensagem de caixa postal para o primeiro usuário.
  
```
$credential = Get-Credential "litwareinc\pilar"

Test-CsExUMVoiceMail -TargetFqdn "atl-cs-001.litwareinc.com" -ReceiverSipAddress "sip:kenmyer@litwareinc.com" -SenderSipAddress "sip:pilar@litwareinc.com" -SenderCredential $credential
```


