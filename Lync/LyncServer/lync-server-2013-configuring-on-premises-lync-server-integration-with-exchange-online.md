---
title: Configurando a integração do Lync Server no local com o Exchange Online
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring on-premises Lync Server integration with Exchange Online
ms:assetid: 95a20117-2064-43c4-94fe-cac892cadb6f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh533880(v=OCS.15)
ms:contentKeyID: 48184900
ms.date: 03/30/2018
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c4900beab738f9aa792919cceec015bb0c3ad0f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-on-premises-lync-server-2013-integration-with-exchange-online"></a>Configurando a integração do Lync Server 2013 local com o Exchange Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2018-03-30_

Os clientes que usam implantações locais do Lync Server 2013 podem configurar a interoperabilidade com o Microsoft Outlook Web App no Microsoft Exchange Online em um modo de implantação híbrida. Recursos de interoperabilidade incluem logon único, sistemas de mensagens instantâneas (IM) e integração de presença com a interface do Outlook Web App. Para habilitar essa integração, você deve configurar o servidor de borda em sua implantação local do Lync Server, realizando as seguintes tarefas:

  - Configurar um espaço de endereçamento SIP compartilhado

  - Configurar um provedor de hospedagem no servidor de borda

  - Verificar a replicação do repositório de gerenciamento central atualizado

Se o Lync Server 2013 estiver integrado ao Exchange Online, um usuário que está tentando entrar no IM do OWA será considerado um usuário remoto ou externo. Neste cenário, esse usuário deve ter uma política de acesso externo atribuída que tenha a opção a seguir selecionada:

**Permitir comunicações com usuários remotos**

Habilite essa opção se quiser que os usuários em sua organização que estejam fora do firewall, como telecomutadores e usuários que estão viajando, possam se conectar ao Lync Server pela Internet.

Para obter mais informações, consulte [gerenciar política de acesso externo no Lync Server 2013](lync-server-2013-manage-external-access-policy-for-your-organization.md).

<div>

## <a name="configure-a-shared-sip-address-space"></a>Configurar um espaço de endereçamento SIP compartilhado

Para integrar o Lync Server 2013 local com o Exchange Online, você deve configurar um espaço de endereçamento SIP compartilhado. O mesmo espaço de endereço de domínio SIP é compatível com o Lync Server e o serviço do Exchange Online.

Usando o Shell de gerenciamento do Lync Server, configure o servidor de borda para Federação executando o cmdlet **set-CSAccessEdgeConfiguration** , usando os parâmetros exibidos no exemplo a seguir:

    Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

  - **AllowFederatedUsers** especifica se os usuários internos têm permissão para se comunicar com usuários de domínios federados. Essa propriedade também determina se os usuários internos podem se comunicar com usuários em um cenário de espaço de endereçamento SIP compartilhado com o Lync Server e o Exchange Online.

Para obter detalhes sobre como usar o Shell de gerenciamento do Lync Server, consulte [Lync server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md).

</div>

<div>

## <a name="configure-a-hosting-provider-on-the-edge-server"></a>Configurar um provedor de hospedagem no Servidor de Borda

Use o Shell de gerenciamento do Lync Server para configurar um provedor de hospedagem no servidor de borda. Para fazer isso, execute o cmdlet **New-CsHostingProvider** usando os parâmetros no exemplo a seguir:

    New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification

<div>


> [!NOTE]
> Se você estiver usando o Office 365 operado pela 21Vianet na China, substitua o valor para o parâmetro <STRONG>ProxyFqdn</STRONG> neste exemplo ("exap.um.Outlook.com") com o FQDN para o serviço operado pela 21vianet: "exap.um.Partner.Outlook.cn".



</div>

  - **Identity** especifica um identificador de valor de cadeia de caracteres exclusivo para o provedor de hospedagem que você está criando (por exemplo, "Exchange Online"). Os valores que contêm espaços devem estar entre aspas duplas.

  - **Habilitado** indica se a conexão de rede entre seu domínio e o provedor de hospedagem está habilitado. Isso deve ser definido como **true**.

  - **EnabledSharedAddressSpace**indica se o provedor de hospedagem será usado no cenário de espaço de endereçamento SIP compartilhado. Isso deve ser definido como **true**.

  - **HostsOCSUsers** indica se o provedor de hospedagem é usado para hospedar o Office Communications Server ou o Lync Server. Isso deve ser definido como **false**.

  - **ProxyFQDN** especifica o FQDN (nome de domínio totalmente qualificado) para o servidor proxy usado pelo provedor de hospedagem. Para o Exchange Online, o FQDN é exap.um.outlook.com.

  - **IsLocal** indica se o servidor proxy usado pelo provedor de hospedagem está contido em sua topologia do Lync Server. Isso deve ser definido como **false**.

  - **VerificationLevel** indica o nível de verificação permitido para mensagens enviadas de e para o provedor hospedado. Especifique **UseSourceVerification**. Essa opção depende do nível de verificação incluído nas mensagens enviadas do provedor de hospedagem. Se esse nível não for especificado, a mensagem será rejeitada como não verificável.

</div>

<div>

## <a name="verify-replication-of-the-updated-central-management-store"></a>Verificar a replicação do Repositório de Gerenciamento Central Atualizado

As alterações feitas usando os cmdlets nas seções anteriores são automaticamente aplicadas ao servidor de borda e geralmente levam menos de um minuto para serem replicadas. Você pode verificar o status de replicação e se as alterações foram aplicadas ao servidor de borda usando os cmdlets a seguir.

Para verificar as atualizações de replicação em um servidor interno na sua implantação do Lync Server, execute o seguinte cmdlet:

    Get-CsManagementStoreReplicationStatus

Para verificar se as alterações foram aplicadas, execute o seguinte cmdlet no servidor de borda:

    Get-CsHostingProvider -LocalStore

</div>

<div>

## <a name="see-also"></a>Confira também


[Fornecimento de mensagens de voz para usuários do Lync Server 2013 no Exchange UM hospedado](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)  
[Integração de Unificação de mensagens do Exchange hospedada no Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

