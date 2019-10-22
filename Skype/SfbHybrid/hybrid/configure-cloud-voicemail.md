---
title: Configurar o serviço de caixa postal na nuvem para usuários locais
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Instruções para implementar a caixa postal baseada em nuvem para usuários hospedados no Skype for Business Server.
ms.openlocfilehash: 7423f16e7985a063ae5a974ea6c36684bfb75e7c
ms.sourcegitcommit: 0de27096ea3c9d6f210aeb4aad31c4255c3c0244
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/21/2019
ms.locfileid: "37616064"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Configurar o serviço de caixa postal na nuvem para usuários locais

## <a name="overview"></a>Visão geral 
Este artigo descreve como configurar o serviço de caixa postal do Microsoft Cloud para seus usuários locais do Skype for Business.  

Este artigo pressupõe que você já tem o Skype for Business Server implantado em uma topologia com suporte e que você atende aos pré-requisitos para a configuração da conectividade híbrida.

Para obter mais informações sobre os benefícios, considerações de planejamento e requisitos para a implementação da caixa postal em nuvem, consulte [Plan Cloud Cloud Service](plan-cloud-voicemail.md).




A configuração da caixa postal em nuvem envolve as seguintes tarefas:

1.  Verifique se você atende aos pré-requisitos, conforme descrito em [Plan Cloud Cloud Service](plan-cloud-voicemail.md).

2.  Verifique se você configurou a conectividade híbrida conforme descrito em [Plan Hybrid Connectivity](plan-hybrid-connectivity.md) e [Configure Hybrid Connectivity](configure-hybrid-connectivity.md). 

3.  [Configure a caixa postal na nuvem como o provedor de hospedagem no servidor de borda](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) , conforme descrito neste artigo.

4.  [Configure uma política de caixa postal hospedada](#configure-a-hosted-voicemail-policy) , conforme descrito neste artigo.

5.  [Atribua uma política de caixa postal hospedada](#assign-a-hosted-voicemail-policy) , conforme descrito neste artigo.

6.  [Habilitar um usuário para caixa postal na nuvem](#enable-a-user-for-cloud-voicemail) , conforme descrito neste artigo.


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a>Configurar a caixa postal na nuvem como o provedor de hospedagem no servidor de borda 

Você configura a caixa postal na nuvem como o provedor de hospedagem em um servidor front-end usando o cmdlet New-CsHostingProvider com os seguintes parâmetros:

- **Identity** especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando; por exemplo, caixa postal em nuvem. 

- **Habilitado** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. Esse parâmetro deve ser definido como true.

- **EnabledSharedAddressSpace**indica se o provedor de hospedagem será usado no cenário de espaço de endereçamento SIP compartilhado. Esse parâmetro deve ser definido como true.

- **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar contas do Skype for Business Server. Esse parâmetro deve ser definido como false.

- **ProxyFQDN** especifica o nome de domínio totalmente qualificado (FQDN) para o servidor proxy usado pelo provedor de hospedagem; por exemplo, proxyserver.contoso.com. Entre em contato com seu provedor de hospedagem por esta informação. Este valor não pode ser modificado. Se o provedor de hospedagem alterar seu servidor proxy, será necessário excluir e recriar a entrada desse provedor.

- **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia do Skype for Business Server. Esse parâmetro deve ser definido como false.

Por exemplo, no Shell de gerenciamento do Skype for Business, o seguinte cmdlet configura a caixa postal na nuvem como o provedor de hospedagem:


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurar uma política de caixa postal hospedada

Para garantir que a caixa postal de sua organização seja encaminhada para o serviço de caixa postal na nuvem, você deve configurar uma política de caixa postal hospedada para sua organização. Em muitos casos, apenas uma política de caixa postal hospedada é necessária e você pode modificar a política global para atender a todas as suas necessidades. Se sua organização requer várias políticas de caixa postal hospedadas, você pode adicionar políticas usando o cmdlet New-CsHostedVoiceMailPolicy.

Para modificar a política global, execute o seguinte comando no Shell de gerenciamento do Skype for Business Server após atualizar sua organização e Tenantid:

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -Tenant “11111111-1111-1111-1111-111111111111”
```

- **Destination** especifica o FQDN (nome de domínio totalmente qualificado) do serviço de caixa postal hospedado na nuvem. Esse valor deve ser definido como **exap.um.Outlook.com**.

- **Organização** é o domínio padrão atribuído ao seu locatário. Você pode recuperar essas informações com o administrador de locatários para fazer logon no office.com, clique no aplicativo do centro de administração, navegue até a **instalação** à esquerda e clique em **domínios**. Por exemplo: mytenant.onmicrosoft.com.

    O nome da organização também é o nome de domínio padrão no Office 365.

- O **locatário** é usado para identificar seu locatário no Office 365. Para obter mais informações, consulte [Find Your Office 365 locatário ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).

Para garantir que uma política de caixa postal hospedada seja criada com êxito, execute o seguinte comando:

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Atribuir uma política de caixa postal hospedada

Por padrão, a política de caixa postal hospedada global é atribuída a todos os usuários. Se você usar uma política diferente, antes de habilitar os usuários para caixa postal hospedada, deverá primeiro conceder aos usuários a política de caixa postal hospedada desejada usando o cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .

Por exemplo, o seguinte comando atribui uma política de caixa postal hospedada não global a um usuário:


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Habilitar um usuário para caixa postal em nuvem

Para permitir que as chamadas de caixa postal de um usuário sejam encaminhadas para a caixa postal na nuvem, use o cmdlet [set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) com o parâmetro HostedVoiceMail. 

Por exemplo, o seguinte comando habilita uma conta de usuário para caixa postal em nuvem: 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

O cmdlet verifica se a política de caixa postal da nuvem, no nível global, de site ou de usuário, se aplica a este usuário. Se nenhuma política for aplicada, o cmdlet falhará.  

O próximo exemplo desabilita uma conta de usuário para a caixa postal na nuvem:

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

O cmdlet verifica se nenhuma política de caixa postal hospedada, no nível global, de site ou de usuário, se aplica a este usuário. Se uma política for aplicada, o cmdlet falhará.

> [!NOTE]
>  Os usuários devem ter o Enterprise-Voice habilitado para usar o serviço de caixa postal do Microsoft Cloud.
