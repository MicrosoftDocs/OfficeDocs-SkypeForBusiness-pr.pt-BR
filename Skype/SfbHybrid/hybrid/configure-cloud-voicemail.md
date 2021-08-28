---
title: Configurar Caixa postal na Nuvem serviço para usuários locais
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection: ''
description: Instruções para implementar a caixa postal baseada em nuvem para usuários que estão Skype for Business Server.
ms.openlocfilehash: 4f38c181c84edb695fce54d6da805482563cfe01
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58625743"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Configurar Caixa postal na Nuvem serviço para usuários locais

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


## <a name="overview"></a>Visão Geral 
Este artigo descreve como configurar um serviço Caixa postal na Nuvem da Microsoft para seus usuários Skype for Business locais.  

Este artigo pressupa que você já Skype for Business Server implantado em uma topologia com suporte e que você atendeu aos pré-requisitos para configurar a conectividade híbrida.

Para obter mais informações sobre os benefícios, considerações de planejamento e requisitos para implementar Caixa postal na Nuvem, consulte [Plan Caixa postal na Nuvem service](plan-cloud-voicemail.md).




A configuração Caixa postal na Nuvem envolve as seguintes tarefas:

1.  Verifique se você atendeu aos pré-requisitos conforme descrito em [Plan Caixa postal na Nuvem service](plan-cloud-voicemail.md).

2.  Verifique se você configurou a conectividade híbrida conforme descrito em [Plan hybrid connectivity e](plan-hybrid-connectivity.md) Configure hybrid [connectivity](configure-hybrid-connectivity.md). 

3.  [Configure Caixa postal na Nuvem como o provedor de hospedagem no Servidor Front-End](#configure-cloud-voicemail-as-the-hosting-provider) conforme descrito neste artigo.

4.  [Configure uma política de caixa postal hospedada](#configure-a-hosted-voicemail-policy) conforme descrito neste artigo.

5.  [Atribua uma política de caixa postal hospedada](#assign-a-hosted-voicemail-policy) conforme descrito neste artigo.

6.  [Habilitar um usuário para Caixa postal na Nuvem](#enable-a-user-for-cloud-voicemail) conforme descrito neste artigo.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>Configurar Caixa postal na Nuvem como provedor de hospedagem 

Você configura Caixa postal na Nuvem como provedor de hospedagem em um Servidor Front-End usando o cmdlet New-CsHostingProvider com os seguintes parâmetros:

- **Identity** especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando; por exemplo, Caixa postal na Nuvem. 

- **Habilitado** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. Esse parâmetro deve ser definido como True.

- **EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado no cenário de espaço de endereçamento SIP compartilhado. Esse parâmetro deve ser definido como True.

- **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar Skype for Business Server contas. Esse parâmetro deve ser definido como False.

- **ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem; por exemplo, proxyserver.contoso.com. Entre em contato com seu provedor de hospedagem por esta informação. Este valor não pode ser modificado. Se o provedor de hospedagem mudar seu servidor proxy, você precisará excluir e, em seguida, re-criar a entrada para esse provedor.

- **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia Skype for Business Server local. Esse parâmetro deve ser definido como False.

Por exemplo, no shell Skype for Business Gerenciamento, o seguinte cmdlet configura Caixa postal na Nuvem como provedor de hospedagem:


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurar uma política de caixa postal hospedada

Para garantir que a caixa postal da sua organização seja roteada para o serviço Caixa postal na Nuvem, você deve configurar uma política de caixa postal hospedada para sua organização. Em muitos casos, apenas uma política de caixa postal hospedada é necessária e você pode modificar a política global para atender a todas as suas necessidades. Se sua organização exigir várias políticas de caixa postal hospedadas, você poderá adicionar políticas usando o cmdlet new-cshostedvoicemailpolicy.

Para modificar a política global, execute o seguinte comando no shell de gerenciamento Skype for Business Server após atualizar sua Organização e TenantID:

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **Destination** especifica o FQDN (nome de domínio totalmente qualificado) do serviço Caixa postal na Nuvem hospedado. Esse valor deve ser definido como **exap.um.outlook.com**.

- **A** organização é o domínio padrão atribuído ao seu locatário. Você pode recuperar essas informações fazendo com que o administrador de locatário faça logoff office.com, clique no aplicativo centro de administração, navegue até **Instalação** à esquerda e clique em **Domínios**. Por exemplo: mytenant.onmicrosoft.com.

    O nome da organização também é o nome de domínio padrão Microsoft 365 ou Office 365.

Para garantir que uma política de caixa postal hospedada tenha sido criada com êxito, execute o seguinte comando:

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Atribuir uma política de caixa postal hospedada

Por padrão, a política de caixa postal hospedada global é atribuída a todos os usuários. Se você usar uma política diferente, antes de habiliar usuários para caixa postal hospedada, primeiro você deve conceder aos usuários a política de caixa postal hospedada desejada usando o cmdlet [Grant-CSHostedVoicemailPolicy.](/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)

Por exemplo, o seguinte comando atribui uma política de caixa postal hospedada não Global a um usuário:


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Habilitar um usuário para Caixa postal na Nuvem

Para habilitar as chamadas de caixa postal de um usuário a serem roteadas para Caixa postal na Nuvem, use o cmdlet [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) com o parâmetro HostedVoiceMail. 

Por exemplo, o comando a seguir habilita uma conta de usuário para Caixa postal na Nuvem: 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

O cmdlet verifica se uma política de Caixa postal na Nuvem no nível global, do site ou do usuário se aplica a esse usuário. Se nenhuma política se aplicar, o cmdlet falhará.  

O próximo exemplo desabilita uma conta de usuário para Caixa postal na Nuvem:

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

O cmdlet verifica se nenhuma política de caixa postal hospedada no nível global, do site ou do usuário se aplica a esse usuário. Se uma política se aplicar, o cmdlet falhará.

> [!NOTE]
>  Os usuários devem estar habilitados para uso do Serviço de Caixa postal na Nuvem da Microsoft empresarial.