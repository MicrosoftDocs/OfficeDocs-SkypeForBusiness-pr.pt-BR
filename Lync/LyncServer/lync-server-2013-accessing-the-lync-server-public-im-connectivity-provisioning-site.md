---
title: Acessando o site de configuração de conectividade a redes públicas de mensagens instantâneas do Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a6e028afcd3a9affc6c316b7cb373e124e6d5b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836971"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Acessando o site de configuração de conectividade a redes públicas de mensagens instantâneas do Lync Server a partir do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2019-03-22_

O processo de provisionamento da conectividade do Lync-Skype mudou, em comparação com os métodos de provisionamento da PIC anteriores. Este processo de provisionamento pode levar até trinta dias para ser concluído. Recomendamos que você inicie esse processo primeiro, antes de realizar as demais etapas descritas neste documento. Depois que o processo de provisionamento do Lync-Skype for concluído para a sua conta, a conta será ativada e os seus usuários qualificados serão habilitados para conectividade de mensagens de chat públicas.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Para provisionar a conectividade do Lync-Skype, você precisa das seguintes informações:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Número do contrato da Microsoft</p></li>
<li><p>Nome de domínio totalmente qualificado (FQDN) do serviço de Borda de Acesso</p></li>
<li><p>Domínios do protocolo SIP</p></li>
<li><p>Qualquer FQDN adicional do serviço de Borda de Acesso</p></li>
<li><p>Informações de contato</p></li>
</ol></td>
</tr>
</tbody>
</table>

A partir de abril de 2019, interromperemos a coleta e a retenção de informações de contato para clientes provisionados para o Skype Federation pelo website da pic.lync.com. Essa alteração está sendo feita para garantir que o sistema de provisionamento do pic.lync.com respeite as políticas de privacidade da Microsoft. 

Depois que essa alteração ficar em tempo real, não poderemos mais fornecer atualizações de email em alterações de provisionamento pendentes. As alterações de provisionamento de PIC geralmente são concluídas dentro de 24-48 horas após serem inseridas. Se você ainda tiver problemas com a Federação do Skype 48 horas após o envio de uma solicitação de provisionamento, entre em contato com o suporte técnico da Microsoft para investigar ainda mais.

> [!IMPORTANT]
> Como parte dessa mudança, todas as informações de contato inseridas anteriormente serão removidas do nosso sistema até o final de abril de 2019.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Para iniciar o processo de provisionamento para o Lync-conectividade do Skype:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Entre no site, <strong>https://pic.lync.com</strong>usando o Microsoft Windows Live ID.</p></li>
<li><p>Selecione o tipo de contrato de licenciamento da Microsoft.</p></li>
<li><p>Marque a caixa de seleção, verificando se você leu e aceitou os direitos de uso do produto do Lync Server.</p></li>
<li><p>Na página <strong>iniciar uma solicitação de provisionamento</strong> , clique no link apropriado para iniciar uma solicitação de provisionamento:</p></li>
<li><p>Na página <strong>especificar informações de provisionamento</strong> , insira o FQDN do <strong>serviço de borda de acesso</strong>. Por exemplo, <strong>SIP.contoso.com</strong>.</p>



> [!IMPORTANT]
> Após 1º de julho de 2017 a Microsoft exigirá que os clientes tenham o registro SRV DNS de Federação implantado para conectividade de IM pública para continuar a funcionar.

</li>
<li><p>Digite pelo menos um ou mais nomes de domínio SIP e, em seguida, clique em <strong>Adicionar</strong>.</p>



> [!IMPORTANT]
> Pelo menos um servidor de borda de acesso e um domínio SIP são necessários para concluir o processo de provisionamento. O domínio SIP e o servidor de Borda de Acesso devem estar ativos, em funcionamento e acessíveis na rede.

</li>
<li><p>Na lista de <strong>provedores de serviços públicos de mensagens instantâneas</strong>, selecione <strong>Skype</strong> e clique em <strong>Avançar</strong> para adicionar informações de contato e enviar a solicitação de provisionamento.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Após o envio da solicitação de provisionamento, pode levar até 30 dias para que a conta seja ativada e para que os usuários sejam habilitados para conectividade de IM pública.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitando a federação e a PIC

Depois de enviar a solicitação de provisionamento, você pode se concentrar no ambiente do Lync Server e nas tarefas administrativas necessárias para configurar o Lync-conectividade com o Skype. Nesta seção, presumimos que o administrador do Lync Server implantou o Lync Server e configurou o acesso externo. Para obter informações adicionais sobre como configurar o acesso externo para o Lync Server, consulte "planejando o acesso [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) do usuário externo" em e "Implantando o acesso ao usuário externo" em [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).

Para preparar o ambiente do Lync Server para o Lync-conectividade do Skype, o administrador do Lync Server deve completar as três tarefas a seguir:

<div>

## <a name="1-configure-federation-and-pic"></a>1 \. Configurar a federação e a PIC

A Federação é necessária para permitir que os usuários do Skype se comuniquem com usuários do Lync em sua organização. A PIC (conectividade de mensagens instantâneas) pública é uma classe de Federação e deve ser configurada para permitir que seus usuários do Lync se comuniquem com usuários do Skype. A Federação e a PIC são configuradas usando o painel de controle do Lync Server, mostrado abaixo.

<div>


> [!IMPORTANT]
> A federação de PIC não tem mais suporte no Live Communication Server 2005 SP1 e no Office Communications Server 2007. As plataformas com suporte para a Federação PIC incluem o Lync Server 2013, o Lync Server 2010 e o Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2 \. Configurar pelo menos uma política para dar suporte ao acesso de usuários federados

Usando o painel de controle do Lync Server, um administrador deve configurar uma ou mais políticas de acesso externo do usuário para controlar se os usuários do Skype podem colaborar com usuários internos do Lync Server.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3 \. Configurar a configuração do provedor de PIC da Skype para o Lync

Usando o Shell de gerenciamento do Lync Server, um administrador deve configurar a política de cliente do Lync para exibir o Skype como um provedor de PIC adicional.

<div>


> [!NOTE]
> Os usuários dos provedores de serviços de PIC não podem participar em mensagens instantâneas ou conferências em sua organização até que você também configure pelo menos uma política (etapa 2, anteriormente neste procedimento) para dar suporte à conectividade a redes públicas de mensagens instantâneas. <BR>Para configurar a Federação e a PIC, consulte "habilitar ou desabilitar a Federação e conectividade de <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>im pública" em.<BR>Para configurar pelo menos uma política para dar suporte ao acesso de usuário federado, consulte "configurar políticas para controlar o acesso <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>ao usuário público" em.



</div>

1.  Em um servidor front-end do Lync Server, abra o Shell de gerenciamento do Lync Server.

2.  Execute estes dois comandos:
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > Se você ainda não tiver um provedor PIC em seu ambiente e estiver criando um novo provedor PIC, você não precisará executar o cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Adicionado ao Lync Server 2013 CU5 &amp; o cliente de área de trabalho Lync no Office 2013 SP1, o NameDecorationRoutingDomain e o NameDecorationExcludedDomainList melhoram a situação em que os usuários do Lync adicionam contatos do Skype necessários para "decorar" domínios que não sejam da Microsoft Identifique e encaminhe-os para o Skype (o formato de: usuário (contoso. com) @msn. com). Essas novas configurações permitem a formatação automática dos endereços que o usuário inserir na caixa de diálogo "Adicionar contato do Skype" com o NameDecorationRoutingDomain (que deve ser configurado como msn.com) se não contiver os domínios de NameDecorationExcludedDomainList (no momento, damos suporte a msn.com, live.com, Hotmail.com, outlook.com).

        
        </div>

3.  Em um cliente Lync, agora você pode selecionar Skype como o provedor de PIC e adicionar um cliente Skype especificando a conta da Microsoft. Além disso, um usuário do Skype que mesclou e fez logon com a conta da Microsoft pode enviar solicitação de contato para os usuários do Lync. Para obter mais informações sobre contas da Microsoft, consulte [o que é uma conta da Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Para obter informações adicionais sobre como adicionar clientes ao Lync, consulte [usando o Lync-conectividade do Skype no Lync Server 2013 como usuário final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Para obter informações detalhadas sobre como modificar provedores hospedados, consulte "criar ou editar provedores federados SIP [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)hospedados" em.

Isso conclui as tarefas administrativas que devem ser executadas no servidor. Agora você está pronto para o Lync-conectividade com o Skype.

</div>

</div>

<div>

## <a name="additional-resources"></a>Recursos adicionais

[Usando a conectividade Lync-Skype no Lync Server 2013 como usuário final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Guia de configuração para conectividade Lync-Skype no Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

