---
title: 'Lync Server 2013: habilitando conectividade de Lync-Skype'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Lync-Skype connectivity
ms:assetid: 34c4db3e-582f-41fb-85c4-3438ae02f09f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440170(v=OCS.15)
ms:contentKeyID: 57793361
ms.date: 12/16/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43e26e54d0704ed009af1ef528e60979b759eb69
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528578"
---
# <a name="enabling-lync-skype-connectivity-in-lync-server-2013"></a>Habilitando a conectividade de Lync-Skype no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-12-16_

Depois de enviar a solicitação de provisionamento, você pode se concentrar no ambiente do Lync Server e nas tarefas administrativas necessárias para configurar a conectividade do Lync-Skype. Nesta seção, presumimos que o administrador do Lync Server implantou o Lync Server e configurou o acesso externo. Para obter informações adicionais sobre como configurar o acesso externo para o Lync Server, consulte [Planning for External User Access in Lync server 2013](lync-server-2013-planning-for-external-user-access.md) e [Deploying external User Access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).

Para preparar o ambiente do Lync Server para Lync-Skype conectividade, o administrador do Lync Server deve concluir as três tarefas a seguir:

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Configurar a Federação e a PIC

A Federação é necessária para permitir que os usuários do Skype se comuniquem com usuários do Lync em sua organização. A PIC (conectividade de mensagens instantâneas públicas) é uma classe de Federação e deve ser configurada para permitir que seus usuários do Lync se comuniquem com os usuários do Skype. A Federação e a PIC são configuradas usando o painel de controle do Lync Server, mostrado abaixo.

![Mostrando PIC](images/Dn440170.451b94e3-0b38-488c-835f-1f25690e8074(OCS.15).jpg "Mostrando PIC")

<div>


> [!IMPORTANT]  
> A Federação de PIC não é mais suportada pelo Live Communication Server 2005 SP1 ou pelo Office Communications Server 2007. As plataformas suportadas para Federação img incluem Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Configurar pelo menos uma política para suportar o acesso de usuário federado

Usando o painel de controle do Lync Server, um administrador deve configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários do Skype podem colaborar com usuários internos do Lync Server.

![Políticas](images/Dn440170.8fd46ad1-9749-422c-8c47-c16ac9032cdb(OCS.15).jpg "Políticas")

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Definir a configuração do provedor de PIC do Skype para Lync

Usando o Shell de gerenciamento do Lync Server, um administrador deve configurar a política de cliente do Lync para exibir o Skype como um provedor de PIC adicional.

<div>


> [!NOTE]  
> Os usuários dos provedores de serviços públicos da PIC (conectividade de mensagens instantâneas) não podem participar de mensagens instantâneas ou conferências de áudio ou vídeo em sua organização até que você também configure pelo menos uma política (etapa 2, anteriormente neste procedimento) para dar suporte à conectividade de IM pública.



</div>

1.  Para configurar a Federação e a PIC, consulte "habilitar ou desabilitar Federação e conectividade de IM pública" em [https://go.microsoft.com/fwlink/p/?LinkId=306063](https://go.microsoft.com/fwlink/p/?linkid=306063) .

2.  Para configurar pelo menos uma política para suportar o acesso de usuário federado, consulte "configurar políticas para controlar o acesso de usuário público" em [https://go.microsoft.com/fwlink/p/?LinkId=306064](https://go.microsoft.com/fwlink/p/?linkid=306064) .

**Para editar um provedor existente do Messenger ou do Skype PIC e configurá-lo para o Skype**

1.  Em um servidor front-end do Lync Server, abra o Shell de gerenciamento do Lync Server.

2.  Execute os dois comandos a seguir:
    
    `Remove-CsPublicProvider -Identity <identity-name>`
    
    <div>
    

    > [!NOTE]  
    > Se você ainda não tem um provedor de PIC em seu ambiente e está criando um novo provedor de PIC, não é necessário executar o cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .

    
    </div>
    
    `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
    
    <div>
    

    > [!NOTE]  
    > Adicionado ao Lync Server 2013 CU5 &amp; Lync Desktop Client no Office 2013 SP1, o NameDecorationRoutingDomain e o NameDecorationExcludedDomainList aprimoram a situação em que os usuários do Lync adicionando contatos do Skype necessários para "decorar" domínios que não são da Microsoft para identificar e encaminhá-los ao Skype (o formato de: usuário (contoso. com) @msn. com). Essas novas configurações permitirão a formatação automática do usuário do endereço Enter na caixa de diálogo "Adicionar contato do Skype" com o NameDecorationRoutingDomain (que deve ser definido como msn.com) se ele não contiver os domínios no NameDecorationExcludedDomainList (no momento, podemos oferecer suporte a msn.com, live.com, Hotmail.com, outlook.com).

    
    </div>

3.  A partir de um cliente Lync, agora você pode selecionar Skype como o provedor de PIC e adicionar um cliente Skype especificando sua conta da Microsoft. Além disso, um usuário do Skype que tenha sido mesclado e conectado com a sua conta da Microsoft pode enviar solicitações de contato aos usuários do Lync. Para obter mais informações sobre contas da Microsoft, consulte [o que é uma conta da Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Para obter informações adicionais sobre como adicionar clientes ao Lync, consulte [Using Lync-Skype Connectivity in Lync Server 2013 como um usuário final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).
    
    ![Adicionar contato do Skype](images/Dn440170.df0e6ed9-2374-4dfa-a815-87281989487c(OCS.15).jpg "Adicionar contato do Skype")

4.  Para obter informações detalhadas sobre como modificar provedores hospedados, consulte "criar ou editar provedores federados SIP hospedados" em [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065) .

Isso conclui as tarefas administrativas que devem ser executadas no servidor. Agora você está pronto para a conectividade do Lync-Skype.

</div>

</div>

<span> </span>

</div>

</div>

</div>

