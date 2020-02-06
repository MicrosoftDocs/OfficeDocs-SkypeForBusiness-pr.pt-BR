---
title: Configurar a integração entre o Skype for Business Server local e o Outlook Web App
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Resumo: integre o Skype for Business Server e o Outlook Web App.'
ms.openlocfilehash: 2496cc7c2f357c4e1afa73dea18f304c6a7f9607
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797032"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurar a integração entre o Skype for Business Server local e o Outlook Web App

**Resumo:** Integre o Skype for Business Server e o Outlook Web App.

Os clientes que usam implantações locais do Skype for Business Server podem configurar a interoperabilidade com o Microsoft Outlook Web App no Microsoft Exchange Online em um modo de implantação híbrido. Recursos de interoperabilidade incluem logon único, sistemas de mensagens instantâneas (IM) e integração de presença com a interface do Outlook Web App. Para habilitar essa integração, você deve configurar o servidor de borda na implantação do Skype for Business Server no local completando as seguintes tarefas:

- Configurar um espaço de endereçamento SIP compartilhado

- Configurar um provedor de hospedagem no servidor de borda

- Verificar a replicação do repositório de gerenciamento central atualizado

## <a name="configure-a-shared-sip-address-space"></a>Configurar um espaço de endereçamento SIP compartilhado

Para integrar o Skype for Business Server local com o Exchange Online, você deve configurar um espaço de endereço SIP compartilhado. O mesmo espaço de endereço de domínio SIP é compatível com o Skype for Business Server e com o serviço do Exchange Online.

Usando o Shell de gerenciamento do Skype for Business Server, configure o servidor de borda para Federação executando o cmdlet **set-CSAccessEdgeConfiguration** usando os parâmetros exibidos no seguinte exemplo:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- O parâmetro **AllowFederatedUsers** especifica se usuários internos têm permissão para se comunicar com usuários de domínios federados. Essa propriedade também determina se os usuários internos podem se comunicar com usuários em um cenário de espaço de endereço SIP compartilhado com o Skype for Business Server e Exchange Online.

Para obter detalhes sobre como usar o Shell de gerenciamento do Skype for Business Server, consulte [Shell de gerenciamento do Skype for Business Server](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar um provedor de hospedagem no Servidor de Borda

Usando o Shell de gerenciamento do Skype for Business Server, configure um provedor de hospedagem no servidor de borda executando o cmdlet **New-CsHostingProvider** usando os parâmetros no exemplo a seguir:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Se você estiver usando o Office 365 operado pela 21Vianet na China, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN do serviço operado pela 21Vianet: "exap.um.partner.outlook.cn". Se você estiver usando o Office 365 GCC High, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN para GCC High: "exap.um.office365.us".

- **Identity** especifica um identificador de valor de cadeia de caracteres único para o provedor de hospedagem que está sendo criado (por exemplo "Exchange Online"). Valores que contêm espaços devem estar entre aspas duplas.

- **Habilitado ** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. Deve ser definido como True.

- **EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado em um cenário de espaço de endereçamento SIP compartilhado. Deve ser definido como True.

- **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Office Communications Server ou o Skype for Business Server. Deve ser definido como False.

- **ProxyFQDN** especifica o nome de domínio totalmente qualificado (FQDN) para o servidor de proxy usado pelo provedor de hospedagem. Para o Exchange Online, o FQDN é exap.um.outlook.com.

- **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido na topologia do Skype for Business Server. Deve ser definido como False.

- **VerificationLevel** Indica o nível de verificação permitido para mensagens enviadas de e para o provedor hospedado. Especifique **UseSourceVerification**, que depende do nível de verificação incluído nas mensagens enviadas do provedor de hospedagem. Se esse nível não for especificado, a mensagem será rejeitada como não verificável.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Verificar a replicação do Repositório de Gerenciamento Central Atualizado

As alterações feitas usando cmdlets nas seções anteriores são automaticamente aplicadas ao servidor de borda e geralmente levam menos de um minuto para serem duplicadas. Você pode validar o status da replicação e, em seguida, confirmar que as alterações foram aplicadas ao seu servidor de borda usando os cmdlets a seguir.

Para verificar as atualizações de replicação, em um servidor interno na implantação do Skype for Business Server, execute o seguinte cmdlet:

```powershell
Get-CsManagementStoreReplicationStatus
```
Verifique se o valor UpToDate está sendo exibido como verdadeiro para todas as réplicas.

Para confirmar se as alterações foram aplicadas, no servidor de borda, execute o seguinte cmdlet:

```powershell
Get-CsHostingProvider -LocalStore
```
Verifique se as informações mostradas correspondem às alterações confirmadas nas etapas anteriores.

## <a name="see-also"></a>Confira também

[Fornecer aos usuários do Skype for Business Server o correio de voz no Exchange UM hospedado](https://technet.microsoft.com/library/306d3fb5-231b-4f0b-b8d8-0d9083b5ed77.aspx)

[Integração de Unificação de mensagens do Exchange hospedada no Skype for Business Server](https://technet.microsoft.com/library/f4de0165-da3b-499e-98fc-28ddd0db02d5.aspx)
