---
title: Configurar o serviço de correio de voz de nuvem
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 5/9/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para o correio de voz implementing baseado em nuvem para usuários hospedagem no Skype para Business Server.
ms.openlocfilehash: 80f154a7fa8e34b7912ebf5762e5d0390e21fd22
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294888"
---
# <a name="configure-cloud-voicemail-service"></a>Configurar o serviço de correio de voz de nuvem

## <a name="overview"></a>Visão geral 
Este artigo descreve como configurar o serviço de correio de voz do Microsoft Cloud para seu Skype para usuários do local de negócios.  

Este artigo pressupõe que você já tem Skype para Business Server implantado em uma topologia com suporte e que você cumpre os pré-requisitos para configurar a conectividade híbrida.

Para obter mais informações sobre os benefícios, considerações sobre planejamento e requisitos necessários para implementar a caixa postal de nuvem, consulte [serviço de caixa postal de nuvem planejar](plan-cloud-voicemail.md).




A configuração de caixa postal de nuvem envolve as seguintes tarefas:

1.  Certifique-se de que você cumpre os pré-requisitos conforme descrito no [serviço de caixa postal planejar de nuvem](plan-cloud-voicemail.md).

2.  Certifique-se de que você tiver configurado a conectividade híbrida, conforme descrito em [conectividade de híbrido plano](plan-hybrid-connectivity.md) e [Configure híbrida](configure-hybrid-connectivity.md). 

3.  [Configurar caixa postal de nuvem como o provedor de hospedagem no servidor de borda](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) conforme descrito neste artigo.

4.  [Configure uma política de caixa postal hospedada](#configure-a-hosted-voicemail-policy) conforme descrito neste artigo.

5.  [Atribuir uma política de caixa postal hospedada](#assign-a-hosted-voicemail-policy) , conforme descrito neste artigo.

6.  [Habilitar um usuário para caixa postal de nuvem](#enable-a-user-for-cloud-voicemail) , conforme descrito neste artigo.


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>Configurar caixa postal de nuvem como o provedor de hospedagem no servidor de borda 

Você pode configurar caixa postal de nuvem como o provedor de hospedagem no servidor de borda usando o cmdlet New-CsHostingProvider, com os seguintes parâmetros:

- **Identidade** Especifica um identificador de valor de cadeia de caracteres exclusiva para o provedor de hospedagem que você está criando; Por exemplo, nuvem caixa postal. 

- **Habilitado ** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. Este parâmetro deve ser definido como True.

- **EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado em um cenário de espaço de endereço SIP compartilhado. Este parâmetro deve ser definido como True.

- **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Skype para contas de servidores de negócios. Este parâmetro deve ser definido como False.

- **ProxyFQDN** Especifica o nome de domínio totalmente qualificado (FQDN) para o servidor proxy usado pelo provedor de hospedagem; Por exemplo, proxyserver.contoso.com. Contate seu provedor de hospedagem para essas informações. Esse valor não pode ser modificado. Se o provedor de hospedagem altera seu servidor proxy, você precisará excluir e recriar a entrada desse provedor.

- **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido dentro de sua Skype para a topologia de servidor de negócios. Este parâmetro deve ser definido como False.

Por exemplo, no Skype do shell de gerenciamento de negócios, o cmdlet a seguir configura caixa postal de nuvem como um provedor de hospedagem:


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurar uma política de caixa postal hospedada

Para garantir que caixa postal para sua organização é encaminhada para o serviço de correio de voz de nuvem, você deve configurar uma política de caixa postal hospedada para a sua organização. Em muitos casos, apenas um correio de voz hospedada diretiva é necessária e você pode modificar a política global para atender a todas as suas necessidades. Se sua organização requer várias políticas de caixa postal hospedada, você pode adicionar políticas usando o cmdlet new-cshostedvoicemailpolicy.

Para modificar a política global, execute o seguinte comando no Skype para Business Server shell de gerenciamento após a atualização de sua organização e a TenantID:

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- **Destino** Especifica o nome de domínio totalmente qualificado (FQDN) do serviço de nuvem de caixa postal hospedado. Este valor deve ser definido como **exap**.

- **Organização** é o domínio padrão atribuído ao seu locatário. É possível recuperar essas informações fazendo com que o administrador proprietário faça logon no office.com, clique no aplicativo Admin Center, navegue para a **instalação** à esquerda e clique em **domínios**. Por exemplo: mytenant.onmicrosoft.com.

    O nome da organização também é o nome de domínio padrão no Office 365.

- **TenantID** é usado para identificar o seu locatário do Office 365. Para obter mais informações, consulte [Encontre seu ID de Inquilino do Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).

Para garantir que uma política de caixa postal hospedada foi criada com êxito, execute o seguinte comando:

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Atribuir uma política de caixa postal hospedada

Por padrão, o Global hospedado política de caixa postal é atribuída a todos os usuários. Se você usar uma política diferente, antes de habilitar usuários para caixa postal hospedada, você deve primeiro conceder aos usuários a política de correio de voz hospedada desejado usando o cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .

Por exemplo, o comando a seguir atribui uma política de caixa postal de hospedada não Global a um usuário:


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Habilitar um usuário para caixa postal de nuvem

Para habilitar chamadas de caixa postal de um usuário sejam roteadas para caixa postal de nuvem, você pode usar o cmdlet [Set-CsUser](https://docs.microsoft.com/en-us/powershell/module/skype/set-csuser?view=skype-ps) com o parâmetro HostedVoiceMail. 

Por exemplo, o comando a seguir habilita uma conta de usuário para caixa postal de nuvem: 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

O cmdlet verifica se uma diretiva de caixa postal de nuvem--em escopo global, site ou nível de usuário – se aplica a este usuário. Se nenhuma diretiva aplicável, o cmdlet falhará.  

O próximo exemplo desabilita uma conta de usuário para caixa postal de nuvem:

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

O cmdlet verifica que nenhuma diretiva de caixa postal hospedada--em escopo global, site ou nível de usuário – se aplica a este usuário. Se aplicar uma política, o cmdlet falhará.

> [!NOTE]
>  Os usuários devem ser habilitado para usar o serviço de correio de voz de nuvem da Microsoft enterprise-voice.