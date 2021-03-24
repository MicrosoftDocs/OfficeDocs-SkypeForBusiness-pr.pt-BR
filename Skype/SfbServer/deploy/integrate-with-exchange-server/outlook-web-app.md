---
title: Configurar a integração entre o Skype for Business Server local e o Outlook Web App
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: 'Resumo: Integrar o Skype for Business Server e o Outlook Web App.'
ms.openlocfilehash: daa9430034d82a3a8dee980a9b075b2fc5656c86
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51109687"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurar a integração entre o Skype for Business Server local e o Outlook Web App

**Resumo:** Integre o Skype for Business Server e o Outlook Web App.

Os clientes que estão usando implantações locais do Skype for Business Server podem configurar a interoperabilidade com o Microsoft Outlook Web App Microsoft Exchange Online em um modo de implantação híbrida. Recursos de interoperabilidade incluem logon único, sistemas de mensagens instantâneas (IM) e integração de presença com a interface do Outlook Web App. Para habilitar essa integração, você deve configurar o Servidor de Borda em sua implantação local do Skype for Business Server concluindo as seguintes tarefas:

- Configurar um espaço de endereçamento SIP compartilhado

- Configurar um provedor de hospedagem no Servidor de Borda

- Verificar a replicação do armazenamento de Gerenciamento Central atualizado

## <a name="configure-a-shared-sip-address-space"></a>Configurar um espaço de endereçamento SIP compartilhado

Para integrar o Skype for Business Server local com o Exchange Online, você deve configurar um espaço de endereço SIP compartilhado. O mesmo espaço de endereço de domínio SIP é suportado pelo Skype for Business Server e pelo serviço Exchange Online.

Usando o Shell de Gerenciamento do Skype for Business Server, configure o Servidor de Borda para federação executando o cmdlet **Set-CSAccessEdgeConfiguration,** usando os parâmetros exibidos no exemplo a seguir:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- O parâmetro **AllowFederatedUsers** especifica se usuários internos têm permissão para se comunicar com usuários de domínios federados. Essa propriedade também determina se os usuários internos podem se comunicar com os usuários em um cenário de espaço de endereço SIP compartilhado com o Skype for Business Server e o Exchange Online.

Para obter detalhes sobre como usar o Shell de Gerenciamento do Skype for Business Server, consulte [Skype for Business Server Management Shell](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar um provedor de hospedagem no Servidor de Borda

Usando o Shell de Gerenciamento do Skype for Business Server, configure um provedor de hospedagem no Servidor de Borda executando o cmdlet **New-CsHostingProvider,** usando os parâmetros no exemplo a seguir:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Se você estiver usando o Microsoft 365 ou o Office 365 operado pela 21Vianet na China, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN para o serviço operado pela 21Vianet: "exap.um.partner.outlook.cn". Se você estiver usando o Microsoft 365 ou o Office 365 GCC High, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN para GCC High: "exap.um.office365.us".

- **Identity** especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando (por exemplo, "Exchange Online"). Valores que contêm espaços devem estar entre aspas duplas.

- **Habilitado** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. Deve ser definido como True.

- **EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado no cenário de espaço de endereçamento SIP compartilhado. Deve ser definido como True.

- **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Office Communications Server ou o Skype for Business Server. Deve ser definido como False.

- **ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem. Para o Exchange Online, o FQDN é exap.um.outlook.com.

- **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido na topologia do Skype for Business Server. Deve ser definido como False.

- **VerificationLevel** Indica o nível de verificação permitido para mensagens enviadas de e para o provedor hospedado. Especifique **UseSourceVerification**, que depende do nível de verificação incluído nas mensagens enviadas do provedor de hospedagem. Se esse nível não for especificado, a mensagem será rejeitada como não verificável.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Verificar a replicação do Repositório de Gerenciamento Central Atualizado

As alterações feitas usando os cmdlets nas seções anteriores são aplicadas automaticamente ao Servidor de Borda e geralmente levam menos de um minuto para replicar. Você pode validar o status da replicação e confirmar se as alterações foram aplicadas ao Servidor de Borda usando os cmdlets a seguir.

Para verificar as atualizações de replicação, em um servidor interno em sua implantação do Skype for Business Server, execute o seguinte cmdlet:

```powershell
Get-CsManagementStoreReplicationStatus
```
Verifique se o valor UpToDate está mostrando TRUE para todas as réplicas.

Para confirmar se as alterações foram aplicadas, no Servidor de Borda, execute o seguinte cmdlet:

```powershell
Get-CsHostingProvider -LocalStore
```
Verifique duas vezes se as informações mostradas coincidem com as alterações comprometidas nas etapas anteriores.

## <a name="see-also"></a>Confira também

[Fornecendo caixa postal para usuários do Skype for Business Server na UM do Exchange hospedada](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[Integração de Unificação de Mensagens do Exchange hospedada no Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)