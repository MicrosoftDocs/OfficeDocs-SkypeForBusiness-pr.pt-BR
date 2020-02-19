---
title: Acessando o site de provisionamento da conectividade de IM pública do Lync Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Accessing the Lync Server public IM connectivity provisioning site
ms:assetid: 77a08234-6bcf-4f59-b43b-ee5fc1926585
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440174(v=OCS.15)
ms:contentKeyID: 57793364
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f73ed3cfaae6edb7fa6bcd2db33197fcc6dfe97c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="accessing-the-lync-server-public-im-connectivity-provisioning-site-from-lync-server-2013"></a>Acessando o site de provisionamento da conectividade de IM pública do Lync Server do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2019-03-22_

O processo de provisionamento para a conectividade Lync-Skype foi alterado, em comparação aos métodos de provisionamento PIC anteriores. Esse processo de provisionamento pode levar até trinta dias para ser concluído. Recomendamos que você inicie esse processo primeiro, antes de concluir as etapas restantes deste documento. Após a conclusão do processo de provisionamento do Lync-Skype para sua conta, a conta é ativada e seus usuários qualificados estão habilitados para conectividade de IM pública.

### <a name="to-provision-lync-skype-connectivity-you-need-the-following-information"></a>Para provisionar a conectividade do Lync-Skype, você precisa das seguintes informações:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Número de contrato da Microsoft</p></li>
<li><p>Nome de domínio totalmente qualificado (FQDN) do serviço de borda de acesso</p></li>
<li><p>Domínio (s) do protocolo de iniciação de sessão (SIP)</p></li>
<li><p>Todos os FQDNs de serviço de borda de acesso adicional</p></li>
<li><p>Informações de contato</p></li>
</ol></td>
</tr>
</tbody>
</table>

A partir de abril de 2019, interromperemos a coleta e a retenção de informações de contato para clientes que foram provisionados para Federação do Skype por meio do site do pic.lync.com. Essa alteração está sendo feita para garantir que o sistema de provisionamento do pic.lync.com esteja em conformidade com as políticas de privacidade da Microsoft. 

Assim que essa alteração for ativa, não será mais possível fornecer atualizações de email em alterações de provisionamento pendentes. As alterações de provisionamento de PIC normalmente são concluídas em 24-48 horas após serem inseridas. Se você ainda estiver enfrentando problemas de Federação do Skype 48 horas após o envio de uma solicitação de provisionamento, envolva o suporte técnico da Microsoft para investigar ainda mais.

> [!IMPORTANT]
> Como parte dessa alteração, todas as informações de contato inseridas anteriormente serão removidas do nosso sistema até o final de abril de 2019.

### <a name="to-initiate-the-provisioning-process-for-lync-skype-connectivity"></a>Para iniciar o processo de provisionamento para a conectividade Lync-Skype:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ol>
<li><p>Entre no site, <strong>https://pic.lync.com</strong>usando o Microsoft Windows Live ID.</p></li>
<li><p>Selecione o tipo de contrato de licenciamento da Microsoft.</p></li>
<li><p>Marque a caixa de seleção, verificando se você leu e aceitou os direitos de uso do produto para o Lync Server.</p></li>
<li><p>Na página <strong>iniciar uma solicitação de provisionamento</strong> , clique no link apropriado para iniciar uma solicitação de provisionamento:</p></li>
<li><p>Na página <strong>especificar informações de provisionamento</strong> , insira o FQDN do <strong>serviço de borda de acesso</strong>. Por exemplo, <strong>SIP.contoso.com</strong>.</p>



> [!IMPORTANT]
> Após 1º de julho de 2017 a Microsoft exigirá que os clientes tenham o registro SRV DNS de Federação implantado para conectividade de IM pública para continuar funcionando.

</li>
<li><p>Insira pelo menos um ou mais nomes de domínio SIP e clique em <strong>Adicionar</strong>.</p>



> [!IMPORTANT]
> É necessário pelo menos um servidor de borda de acesso e um domínio SIP para concluir o processo de provisionamento. O domínio SIP e o servidor de borda de acesso devem estar ativos, funcionando e alcançáveis na rede.

</li>
<li><p>Na lista de <strong>provedores de serviço de mensagens instantâneas públicas</strong>, selecione <strong>Skype</strong> e clique em <strong>Avançar</strong> para adicionar informações de contato e enviar a solicitação de provisionamento.</p></li>
</ol></td>
</tr>
</tbody>
</table>


Após o envio da solicitação de provisionamento, pode levar até 30 dias para que a conta seja ativada e para que os usuários sejam habilitados para conectividade de IM pública.

<div>

## <a name="enabling-federation-and-public-im-connectivity-pic"></a>Habilitando Federação e conectividade pública de IM (PIC)

Depois de enviar a solicitação de provisionamento, você pode se concentrar no ambiente do Lync Server e nas tarefas administrativas necessárias para configurar a conectividade Lync-Skype. Nesta seção, presumimos que o administrador do Lync Server implantou o Lync Server e configurou o acesso externo. Para obter informações adicionais sobre como configurar o acesso externo para o Lync Server, consulte "planejando o acesso [https://go.microsoft.com/fwlink/p/?LinkID=273772](https://go.microsoft.com/fwlink/p/?linkid=273772) de usuários externos" em e "Implantando o acesso de usuário externo" em [https://go.microsoft.com/fwlink/p/?LinkID=27378](https://go.microsoft.com/fwlink/p/?linkid=27378).

Para preparar o ambiente do Lync Server para a conectividade Lync-Skype, o administrador do Lync Server deve concluir as três tarefas a seguir:

<div>

## <a name="1-configure-federation-and-pic"></a>1\. Configurar a Federação e a PIC

A Federação é necessária para permitir que os usuários do Skype se comuniquem com usuários do Lync em sua organização. A PIC (conectividade de mensagens instantâneas públicas) é uma classe de Federação e deve ser configurada para permitir que seus usuários do Lync se comuniquem com os usuários do Skype. A Federação e a PIC são configuradas usando o painel de controle do Lync Server, mostrado abaixo.

<div>


> [!IMPORTANT]
> A Federação de PIC não é mais suportada pelo Live Communication Server 2005 SP1 ou pelo Office Communications Server 2007. As plataformas suportadas para Federação img incluem Lync Server 2013, Lync Server 2010 e Office Communications Server 2007 R2.



</div>

</div>

<div>

## <a name="2-configure-at-least-one-policy-to-support-federated-user-access"></a>2\. Configurar pelo menos uma política para suportar o acesso de usuário federado

Usando o painel de controle do Lync Server, um administrador deve configurar uma ou mais políticas de acesso de usuário externo para controlar se os usuários do Skype podem colaborar com usuários internos do Lync Server.

</div>

<div>

## <a name="3-configure-the-skype-pic-provider-setting-for-lync"></a>3\. Definir a configuração do provedor de PIC do Skype para Lync

Usando o Shell de gerenciamento do Lync Server, um administrador deve configurar a política de cliente do Lync para exibir o Skype como um provedor de PIC adicional.

<div>


> [!NOTE]
> Os usuários dos provedores de serviços públicos da PIC (conectividade de mensagens instantâneas) não podem participar de IM ou conferências em sua organização até que você também configure pelo menos uma política (etapa 2, anteriormente neste procedimento) para dar suporte à conectividade de IM pública.<BR>Para configurar a Federação e a PIC, consulte "habilitar ou desabilitar Federação e conectividade de IM <A href="https://go.microsoft.com/fwlink/p/?linkid=306063">https://go.microsoft.com/fwlink/p/?LinkId=306063</A>pública" em.<BR>Para configurar pelo menos uma política para suportar o acesso de usuário federado, consulte "configurar políticas para controlar o acesso de <A href="https://go.microsoft.com/fwlink/p/?linkid=306064">https://go.microsoft.com/fwlink/p/?LinkId=306064</A>usuário público" em.



</div>

1.  Em um servidor front-end do Lync Server, abra o Shell de gerenciamento do Lync Server.

2.  Execute os dois comandos a seguir:
    
      - `Remove-CsPublicProvider -Identity <identity-name>`
        
        <div>
        

        > [!NOTE]
        > Se você ainda não tem um provedor de PIC em seu ambiente e está criando um novo provedor de PIC, não é necessário executar o cmdlet <STRONG>Remove-CsPublicProvider</STRONG> .

        
        </div>
    
      - `New-CsPublicProvider -ProxyFqdn federation.messenger.msn.com -Enabled 1 -Identity Skype  -VerificationLevel 2 -NameDecorationRoutingDomain msn.com -NameDecorationExcludedDomainList "msn.com,outlook.com,live.com,hotmail.com" -IconUrl "https://images.edge.messenger.live.com/Messenger_16x16.png"`
        
        <div>
        

        > [!NOTE]
        > Adicionado ao Lync Server 2013 CU5 &amp; Lync Desktop Client no Office 2013 SP1, o NameDecorationRoutingDomain e o NameDecorationExcludedDomainList aprimoram a situação em que os usuários do Lync adicionando contatos do Skype necessários para "decorar" domínios que não são da Microsoft para identificar e encaminhá-los ao Skype (o formato de: usuário (contoso. com) @msn. com). Essas novas configurações permitirão a formatação automática do usuário do endereço Enter na caixa de diálogo "Adicionar contato do Skype" com o NameDecorationRoutingDomain (que deve ser definido como msn.com) se ele não contiver os domínios no NameDecorationExcludedDomainList ( no momento, podemos oferecer suporte a msn.com, live.com, Hotmail.com, outlook.com).

        
        </div>

3.  A partir de um cliente Lync, agora você pode selecionar Skype como o provedor de PIC e adicionar um cliente Skype especificando sua conta da Microsoft. Além disso, um usuário do Skype que tenha sido mesclado e conectado com a sua conta da Microsoft pode enviar solicitações de contato aos usuários do Lync. Para obter mais informações sobre contas da Microsoft, consulte [o que é uma conta da Microsoft?](https://support.skype.com/en/faq/fa12059/what-is-a-microsoft-account). Para obter informações adicionais sobre como adicionar clientes ao Lync, consulte [usando a conectividade Lync-Skype no Lync Server 2013 como um usuário final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md).

4.  Para obter informações detalhadas sobre como modificar provedores hospedados, consulte "criar ou editar provedores federados SIP [https://go.microsoft.com/fwlink/p/?LinkId=306065](https://go.microsoft.com/fwlink/p/?linkid=306065)hospedados" em.

Isso conclui as tarefas administrativas que devem ser executadas no servidor. Agora você está pronto para a conectividade Lync-Skype.

</div>

</div>

<div>

## <a name="additional-resources"></a>Recursos adicionais

[Usando a conectividade Lync-Skype no Lync Server 2013 como um usuário final](lync-server-2013-using-lync-skype-connectivity-as-an-end-user.md)

[Guia de provisionamento para a conectividade Lync-Skype no Lync Server 2013](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

