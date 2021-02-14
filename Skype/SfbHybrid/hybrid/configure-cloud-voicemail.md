---
title: Configurar o serviço de Caixa Postal na Nuvem para usuários locais
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
localization_priority: Normal
ms.collection: ''
description: Instruções para implementar a caixa postal baseada em nuvem para usuários que estão no Skype for Business Server.
ms.openlocfilehash: 29faba6bf092647f0c55899f013c6b4bf146304f
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552577"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a>Configurar o serviço de Caixa Postal na Nuvem para usuários locais

## <a name="overview"></a>Visão geral 
Este artigo descreve como configurar o serviço de Caixa Postal do Microsoft Cloud para seus usuários locais do Skype for Business.  

Este artigo presume que você já tenha implantado o Skype for Business Server em uma topologia com suporte e que atendeu aos pré-requisitos para configurar a conectividade híbrida.

Para obter mais informações sobre os benefícios, considerações de planejamento e requisitos para implementar a Caixa Postal na Nuvem, consulte Plano de serviço de Caixa Postal [na Nuvem.](plan-cloud-voicemail.md)




A configuração da Caixa Postal na Nuvem envolve as seguintes tarefas:

1.  Certifique-se de que você atendeu aos pré-requisitos conforme descrito em Plano de Serviço de Caixa [Postal na Nuvem.](plan-cloud-voicemail.md)

2.  Verifique se você configurou a conectividade híbrida conforme descrito em [Planejar](plan-hybrid-connectivity.md) conectividade híbrida e [configurar a conectividade híbrida.](configure-hybrid-connectivity.md) 

3.  [Configure a Caixa Postal na Nuvem como provedor de hospedagem no Servidor Front-End,](#configure-cloud-voicemail-as-the-hosting-provider) conforme descrito neste artigo.

4.  [Configure uma política de caixa postal hospedada](#configure-a-hosted-voicemail-policy) conforme descrito neste artigo.

5.  [Atribua uma política de caixa postal hospedada](#assign-a-hosted-voicemail-policy) conforme descrito neste artigo.

6.  [Habilita um usuário para Caixa Postal na](#enable-a-user-for-cloud-voicemail) Nuvem conforme descrito neste artigo.


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a>Configurar a Caixa Postal na Nuvem como provedor de hospedagem 

Configure a Caixa Postal na Nuvem como o provedor de hospedagem em um Servidor front-end usando o cmdlet New-CsHostingProvider com os seguintes parâmetros:

- **A** identidade especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando; por exemplo, Caixa Postal na Nuvem. 

- **Habilitado** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. Esse parâmetro deve ser definido como True.

- **EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado no cenário de espaço de endereçamento SIP compartilhado. Esse parâmetro deve ser definido como True.

- **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar contas do Skype for Business Server. Esse parâmetro deve ser definido como False.

- **ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem; por exemplo, proxyserver.contoso.com. Entre em contato com seu provedor de hospedagem por esta informação. Este valor não pode ser modificado. Se o provedor de hospedagem mudar seu servidor proxy, você precisará excluir e, em seguida, re-criar a entrada para esse provedor.

- **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia do Skype for Business Server. Esse parâmetro deve ser definido como False.

Por exemplo, no shell de Gerenciamento do Skype for Business, o cmdlet a seguir configura a Caixa Postal na Nuvem como o provedor de hospedagem:


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a>Configurar uma política de caixa postal hospedada

Para garantir que a caixa postal da sua organização seja roteada para o serviço de Caixa Postal na Nuvem, você deve configurar uma política de caixa postal hospedada para sua organização. Em muitos casos, apenas uma política de caixa postal hospedada é necessária, e você pode modificar a política global para atender a todas as suas necessidades. Se sua organização exigir várias políticas de caixa postal hospedada, você poderá adicionar políticas usando o cmdlet new-cshostedvoicemailpolicy.

Para modificar a política global, execute o seguinte comando no shell de gerenciamento do Skype for Business Server após atualizar sua Organização e TenantID:

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- **O** destino especifica o FQDN (nome de domínio totalmente qualificado) do serviço de Caixa Postal na Nuvem hospedado. Esse valor deve ser definido como **exap.um.outlook.com**.

- **A** organização é o domínio padrão atribuído ao seu locatário. Você pode recuperar essas informações fazendo com que o administrador de locatários entre  no office.com, clique no aplicativo do Centro de Administração, navegue até a Instalação à esquerda e clique em **Domínios.** Por exemplo: mytenant.onmicrosoft.com.

    O nome da organização também é o nome de domínio padrão no Microsoft 365 ou office 365.

Para garantir que uma política de caixa postal hospedada tenha sido criada com êxito, execute o seguinte comando:

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a>Atribuir uma política de caixa postal hospedada

Por padrão, a política de caixa postal hospedada global é atribuída a todos os usuários. Se você usar uma política diferente, antes de habilenciar usuários para caixa postal hospedada, primeiro conceda aos usuários a política de caixa postal hospedada desejada usando o cmdlet [Grant-CSHostedVoicemailPolicy.](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps)

Por exemplo, o seguinte comando atribui uma política de caixa postal hospedada não Global a um usuário:


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -PolicyName "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a>Habilitar um usuário para caixa postal na nuvem

Para permitir que as chamadas de caixa postal de um usuário sejam roteadas para a Caixa Postal na Nuvem, use o cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) com o parâmetro HostedVoiceMail. 

Por exemplo, o comando a seguir habilita uma conta de usuário para Caixa Postal na Nuvem: 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

O cmdlet verifica se uma política de Caixa Postal na Nuvem , no nível global, do site ou do usuário, se aplica a esse usuário. Se nenhuma política se aplicar, o cmdlet falhará.  

O próximo exemplo desabilita uma conta de usuário para Caixa Postal na Nuvem:

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

O cmdlet verifica se nenhuma política de caixa postal hospedada , no nível global, de site ou de usuário, se aplica a esse usuário. Se uma política for aplicada, o cmdlet falhará.

> [!NOTE]
>  Os usuários devem estar habilitados para enterprise-voice para usar o Serviço de Caixa Postal do Microsoft Cloud.
