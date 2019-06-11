---
title: 'Lync Server 2013: Habilitando conectividade Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794d2a71c07e742a3ab5597d4bd2aff77157d675
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Habilitando conectividade Lync-Skype no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-12-16_

Depois de enviar a solicitação de provisionamento, você pode se concentrar no ambiente do Lync Server e nas tarefas administrativas necessárias para configurar o Lync-conectividade com o Skype. Nesta seção, presumimos que o administrador do Lync Server implantou o Lync Server e configurou o acesso externo. Para obter informações adicionais sobre como configurar o acesso externo para o Lync Server, consulte [planejar o acesso de usuários externos no Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [implantar o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Para preparar o ambiente do Lync Server para o Lync-conectividade do Skype, o administrador do Lync Server deve completar as três tarefas a seguir:

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. Configurar a federação e a PIC

A Federação é necessária para permitir que os usuários do Skype se comuniquem com usuários do Lync em sua organização. A PIC (conectividade de mensagens instantâneas) pública é uma classe de Federação e deve ser configurada para permitir que seus usuários do Lync se comuniquem com usuários do Skype. A Federação e a PIC são configuradas usando o painel de controle do Lync Server, mostrado abaixo.

![Mostrando pic] (images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Mostrando pic")

<div>


> [!IMPORTANT]  
> A federação de PIC não tem mais suporte no Live Communication Server 2005 SP1 e no Office Communications Server 2007. As plataformas com suporte para a Federação PIC incluem o Lync Server 2013, o Lync Server 2010 e o Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. Configurar pelo menos uma política para dar suporte ao acesso de usuários federados

Usando o painel de controle do Lync Server, um administrador deve configurar uma ou mais políticas de acesso externo do usuário para controlar se os usuários do Skype podem colaborar com usuários internos do Lync Server.

![Regras] de (images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Regras") de

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Configurar a configuração do provedor de PIC da Skype para o Lync

Usando o Shell de gerenciamento do Lync Server, um administrador deve configurar a política de cliente do Lync para exibir o Skype como um provedor de PIC adicional.

<div>


> [!NOTE]  
> Os usuários dos provedores de serviço de conectividade de mensagens instantâneas (PIC) públicas não podem participar de chats ou videoconferências em sua organização até você também configurar pelo menos uma política (etapa 2, anteriormente neste procedimento) para dar suporte à conectividade de mensagens de chat pública.



</div>

1.  Para configurar a Federação e a PIC, consulte "habilitar ou desabilitar a Federação e conectividade de [http://go.microsoft.com/fwlink/p/?LinkId=306063](http://go.microsoft.com/fwlink/p/?linkid=306063)im pública" em.

2.  Para configurar pelo menos uma política para dar suporte ao acesso de usuário federado, consulte "configurar políticas para controlar o acesso [http://go.microsoft.com/fwlink/p/?LinkId=306064](http://go.microsoft.com/fwlink/p/?linkid=306064)ao usuário público" em.

**Para editar um Messenger existente ou um provedor de PIC da Skype e configurá-lo para o Skype**

1.  Em um servidor front-end do Lync Server, abra o Shell de gerenciamento do Lync Server.

2.  Execute estes dois comandos:
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > Se você ainda não tiver um provedor PIC em seu ambiente e estiver criando um novo provedor PIC, você não precisará executar o cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Adicionado ao Lync Server 2013 CU5 &amp; o cliente de área de trabalho Lync no Office 2013 SP1, o NameDecorationRoutingDomain e o NameDecorationExcludedDomainList melhoram a situação em que os usuários do Lync adicionam contatos do Skype necessários para "decorar" domínios que não sejam da Microsoft Identifique e encaminhe-os para o Skype (o formato de: usuário (contoso. com) @msn. com). Essas novas configurações permitem a formatação automática dos endereços que o usuário inserir na caixa de diálogo "Adicionar contato do Skype" com o NameDecorationRoutingDomain (que deve ser configurado como msn.com) se não contiver os domínios de NameDecorationExcludedDomainList (no momento, damos suporte a msn.com, live.com, Hotmail.com, outlook.com).

    
    </div>

3.  Em um cliente Lync, agora você pode selecionar Skype como o provedor de PIC e adicionar um cliente Skype especificando a conta da Microsoft. Além disso, um usuário do Skype que mesclou e fez logon com a conta da Microsoft pode enviar solicitação de contato para os usuários do Lync. Para obter mais informações sobre contas da Microsoft, consulte [o que é uma conta da Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Para obter informações adicionais sobre como adicionar clientes ao Lync, consulte [usando o Lync-conectividade do Skype no Lync Server 2013 como usuário final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Adicionar contato do Skype] (images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Adicionar contato do Skype")

4.  Para obter informações detalhadas sobre como modificar provedores hospedados, consulte "criar ou editar provedores federados SIP [http://go.microsoft.com/fwlink/p/?LinkId=306065](http://go.microsoft.com/fwlink/p/?linkid=306065)hospedados" em.

Isso conclui as tarefas administrativas que devem ser executadas no servidor. Agora você está pronto para o Lync-conectividade com o Skype.

</div>

</div>

<span> </span>

</div>

</div>

</div>

