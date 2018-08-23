---
title: Configurar a integração entre o local Skype para Business Server e o Outlook Web App
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/7/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Resumo: Integre Skype para Business Server e o Outlook Web App.'
ms.openlocfilehash: 5ad1f6bc898a29c2a5e0f326d3a5edc4d782bab2
ms.sourcegitcommit: 25066ab000f7615aff31f77d9d39c266c65e2aa5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2018
ms.locfileid: "22914093"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurar a integração entre o local Skype para Business Server e o Outlook Web App
 
**Resumo:** Integre Skype para Business Server e o Outlook Web App.
  
Clientes que utilizam o local Skype para implantações de servidor de negócios podem configurar a interoperabilidade com o Microsoft Outlook Web App no Microsoft Exchange Online em um modo de implantação híbrida. Recursos de interoperabilidade incluem logon único, sistemas de mensagens instantâneas (IM) e integração de presença com a interface do Outlook Web App. Para habilitar essa integração, você deverá configurar o servidor de borda na sua Skype local para implantação de servidor de negócios concluindo as seguintes tarefas: 
  
- Configurar um espaço de endereçamento SIP compartilhado
    
- Configurar um provedor de hospedagem no servidor de borda
    
- Verificar a replicação do repositório de gerenciamento Central atualizado
    
## <a name="configure-a-shared-sip-address-space"></a>Configurar um espaço de endereçamento SIP compartilhado

Para integrar o local Skype para Business Server com o Exchange Online, você deve configurar um espaço de endereçamento SIP compartilhado. O mesmo espaço de endereço de domínio SIP é compatível com Skype para Business Server e o serviço do Exchange Online.
  
Usando o Skype do Shell de gerenciamento do servidor de negócios, configure o servidor de borda para federação executando o cmdlet **Set-CSAccessEdgeConfiguration** , usando os parâmetros exibidos no exemplo a seguir:
  
```
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- Parâmetro **AllowFederatedUsers** Especifica se os usuários internos poderão se comunicar com usuários de domínios federados. Essa propriedade também determina se os usuários internos podem se comunicar com usuários em um cenário de espaço de endereço SIP compartilhado com Skype para Business Server e o Exchange Online.
    
Para obter detalhes sobre como usar o Skype do Shell de gerenciamento do servidor de negócios, consulte [Skype do Shell de gerenciamento do servidor de negócios](../../manage/management-shell.md).
  
## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar um provedor de hospedagem no Servidor de Borda

Usando o Skype do Shell de gerenciamento do servidor de negócios, configure um provedor de hospedagem no servidor de borda executando o cmdlet **New-CsHostingProvider** , com os parâmetros do exemplo a seguir:
  
```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Se você estiver usando o Office 365 operado pela 21Vianet na China, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN do serviço operado pela 21Vianet: "exap.um.partner.outlook.cn". Se você estiver usando o Office 365 GCC alta, substituir o valor do parâmetro ProxyFqdn neste exemplo ("exap") com o FQDN para GCC alta: "exap.um.office365.us".
  
- **Identidade** Especifica um identificador de valor de cadeia de caracteres exclusiva para o provedor de hospedagem que você está criando (por exemplo, "Exchange Online"). Valores que contêm espaços devem estar entre aspas duplas.
    
- **Habilitado ** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. Deve ser definido como True.
    
- **EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado em um cenário de espaço de endereço SIP compartilhado. Deve ser definido como True.
    
- **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Office Communications Server ou Skype para Business Server. Deve ser definido como False.
    
- **ProxyFQDN** Especifica o nome de domínio totalmente qualificado (FQDN) para o servidor proxy usado pelo provedor de hospedagem. Para o Exchange Online, o FQDN é exap.um.outlook.com.
    
- **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido dentro de sua Skype para a topologia de servidor de negócios. Deve ser definido como False.
    
- **VerificationLevel** Indica o nível de verificação permitido para mensagens que são enviadas de e para o provedor de hospedagem. Especifique **UseSourceVerification**, que depende do nível de verificação incluído nas mensagens enviadas do provedor de hospedagem. Se este nível não for especificado, a mensagem será rejeitada como sendo não-verificáveis.
    
## <a name="verify-replication-of-the-updated-central-management-store"></a>Verificar a replicação do Repositório de Gerenciamento Central Atualizado

As alterações feitas usando os cmdlets nas seções anteriores são aplicadas automaticamente ao servidor de borda e geralmente levam menos de um minuto para replicar. Você pode validar o status da replicação e, em seguida, confirme que as alterações foram aplicadas ao seu servidor de borda usando os cmdlets a seguir.
  
Para verificar as atualizações de replicação, em um servidor interno à sua Skype para implantação do Business Server, execute o seguinte cmdlet:
  
```
Get-CsManagementStoreReplicationStatus
```

Para confirmar que as alterações foram aplicadas, no servidor de borda, execute o seguinte cmdlet:
  
```
Get-CsHostingProvider -LocalStore
```

## <a name="see-also"></a>Consulte também

[Fornecendo Skype para Business Server caixa postal aos usuários em UM do Exchange hospedado](http://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)
  
[Hospedado integração Exchange Unified Messaging no Skype para Business Server](http://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)