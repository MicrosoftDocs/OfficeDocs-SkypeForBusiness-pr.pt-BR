---
title: Configurar a integração entre o Skype for Business Server local e Outlook Web App
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/7/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
description: 'Resumo: Integre Skype for Business Server e Outlook Web App.'
ms.openlocfilehash: 0284fee227d9adf5560b5f65e56d71c1d46fac0c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397280"
---
# <a name="configure-integration-between-on-premises-skype-for-business-server-and-outlook-web-app"></a>Configurar a integração entre o Skype for Business Server local e Outlook Web App

**Resumo:** Integre Skype for Business Server e Outlook Web App.

Os clientes que estão usando implantações Skype for Business Server locais podem configurar a interoperabilidade com Microsoft Outlook Web App no Microsoft Exchange Online em um modo de implantação híbrida. Recursos de interoperabilidade incluem logon único, sistemas de mensagens instantâneas (IM) e integração de presença com a interface do Outlook Web App. Para habilitar essa integração, você deve configurar o Servidor de Borda em sua implantação local Skype for Business Server concluindo as seguintes tarefas:

- Configurar um espaço de endereçamento SIP compartilhado

- Configurar um provedor de hospedagem no Servidor de Borda

- Verificar a replicação do armazenamento de Gerenciamento Central atualizado

## <a name="configure-a-shared-sip-address-space"></a>Configurar um espaço de endereçamento SIP compartilhado

Para integrar a Skype for Business Server local Exchange Online, você deve configurar um espaço de endereço SIP compartilhado. O mesmo espaço de endereço de domínio SIP é suportado pelo serviço de Skype for Business Server e Exchange Online sip.

Usando o Shell de Gerenciamento Skype for Business Server, configure o Servidor de Borda para federação executando o cmdlet **Set-CSAccessEdgeConfiguration**, usando os parâmetros exibidos no exemplo a seguir:

```powershell
Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True
```

- O parâmetro **AllowFederatedUsers** especifica se usuários internos têm permissão para se comunicar com usuários de domínios federados. Essa propriedade também determina se os usuários internos podem se comunicar com os usuários em um cenário de espaço de endereço SIP compartilhado com Skype for Business Server e Exchange Online.

Para obter detalhes sobre como usar o Shell de Gerenciamento Skype for Business Server, [consulte Skype for Business Server Shell de Gerenciamento](../../manage/management-shell.md).

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar um provedor de hospedagem no Servidor de Borda

Usando o Shell de Gerenciamento Skype for Business Server, configure um provedor de hospedagem no Servidor de Borda executando o cmdlet **New-CsHostingProvider**, usando os parâmetros no exemplo a seguir:

```powershell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

> [!NOTE]
> Se você estiver usando Microsoft 365 ou Office 365 operado pela 21Vianet na China, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN para o serviço operado pela 21Vianet: "exap.um.partner.outlook.cn". Se você estiver usando Microsoft 365 ou Office 365 GCC Alto, substitua o valor do parâmetro ProxyFqdn neste exemplo ("exap.um.outlook.com") pelo FQDN para GCC High: "exap.um.office365.us".

- **Identity** especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando (por exemplo, "Exchange Online"). Valores que contêm espaços devem estar entre aspas duplas.

- **Enabled** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitada. Deve ser definido como True.

- **EnabledSharedAddressSpace** indica se o provedor de hospedagem será usado em um cenário de espaço de endereçamento SIP compartilhado. Deve ser definido como True.

- **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar Office Communications Server ou Skype for Business Server. Deve ser definido como False.

- **ProxyFQDN** especifica o nome de domínio totalmente qualificado (FQDN) para o servidor de proxy usado pelo provedor de hospedagem. Para o Exchange Online, o FQDN é exap.um.outlook.com.

- **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia Skype for Business Server local. Deve ser definido como False.

- **VerificationLevel** Indica o nível de verificação permitido para mensagens enviadas de e para o provedor hospedado. Especifique **UseSourceVerification**, que depende do nível de verificação incluído nas mensagens enviadas do provedor de hospedagem. Se esse nível não for especificado, a mensagem será rejeitada como não verificável.

## <a name="verify-replication-of-the-updated-central-management-store"></a>Verificar a replicação do Repositório de Gerenciamento Central Atualizado

As alterações feitas usando os cmdlets nas seções anteriores são aplicadas automaticamente ao Servidor de Borda e geralmente levam menos de um minuto para replicar. Você pode validar o status da replicação e confirmar se as alterações foram aplicadas ao Servidor de Borda usando os cmdlets a seguir.

Para verificar as atualizações de replicação, em um servidor interno em sua implantação Skype for Business Server, execute o seguinte cmdlet:

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

[Fornecendo Skype for Business Server caixa postal para usuários hospedados Exchange UM](/previous-versions/office/lync-server-2013/lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um)

[Integração Exchange Unificação de Mensagens hospedada no Skype for Business Server](/previous-versions/office/lync-server-2013/lync-server-2013-hosted-exchange-unified-messaging-integration)