---
title: 'Lync Server 2013: alterar a URL dos serviços Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 335c73a56da1d8b9a28e7089a7cc2238724a322b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-the-web-services-url-in-lync-server-2013"></a>Alterar a URL dos serviços Web no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2015-11-16_

Ao configurar os seus pools front-end e os servidores padrão da edição, você tem a opção de configurar um FQDN (nome de domínio totalmente qualificado) do Web farm externo e portas associadas. Se você não configurou esta URL ao executar o assistente de implantação do Lync Server, será necessário definir manualmente essas configurações. Geralmente, um administrador não precisa modificar essas configurações, pois essas são as portas recomendadas e padrão.

<div>


> [!NOTE]  
> A captura de tela a seguir foi realizada durante a configuração de um servidor Standard Edition, portanto, a opção substituir FQDN está desabilitada. Essa opção é habilitada ao configurar um servidor Enterprise Edition em um pool de front-ends.



</div>

![Editar configurações do pool de serviços Web] (images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Editar configurações do pool de serviços Web")

<div>

## <a name="to-configure-web-services"></a>Para configurar serviços Web

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

3.  No construtor de topologia, na árvore de console, em **servidores front-end da edição padrão**, **pools front-end do Enterprise Edition**e pools de **diretórios**, selecione o nome do pool. Clique com o botão direito do mouse no nome, clique em **Editar propriedades**e, em seguida, clique em **Serviços Web**.

4.  Adicione ou edite o **FQDN dos serviços Web externos**e clique em **OK**.
    
    <div>
    

    > [!WARNING]  
    > Se você tiver mais de um servidor front-end ou servidor front-end, os serviços Web externos FQDN deverão ser exclusivos. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-end ou servidor front-end. Se você também estiver implantando diretores, os serviços Web externos FQDN definidos para qualquer diretor de director ou diretor devem ser exclusivos de qualquer outro diretor ou pool de director, bem como qualquer pool de front-end ou servidor front-end.

    
    </div>

5.  Verifique se as portas de escuta e publicadas estão configuradas corretamente para o seu ambiente.

6.  Repita essas etapas para todos os servidores de edição padrão, pools de front-end e pools de directors em seu ambiente.

7.  Na árvore de console, clique em **Lync Server 2013**e, em seguida, no painel **ações** , clique em **publicar topologia**.

Há alguns requisitos dos quais você deve estar ciente ao configurar as portas de escuta e publicação:

  - As portas de escuta mostradas são as portas configuradas para o IIS (servidor de informações da Internet) em cada servidor front-end.

  - As portas de escuta internas e externas devem ser diferentes para o IIS. Para as portas de escuta externas, elas são geralmente iguais porque representam o balanceador de carga de hardware para tráfego da Web interno e um representa o servidor proxy reverso para tráfego da Web externo.

  - Você pode substituir os serviços Web internos em um pool de front-end, diretor ou um pool de directors e definir seu próprio FQDN.
    
    <div>
    

    > [!WARNING]  
    > Se você decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.

    
    </div>

  - As portas publicadas devem ser configuradas no balanceamento de carga de hardware ou proxy reverso como portas de escuta.

  - Para um pool de front-ends (não mostrado no exemplo), o FQDN do pool de SIP interno deve ser diferente do FQDN de serviços Web internos, porque o tráfego da Web chega ao balanceador de carga de hardware e o tráfego do pool SIP interno percorre o balanceador de carga de DNS . Este requisito deve ser atendido.

  - Uma implantação do Lync Server Standard Edition não precisa ou permite que um FQDN de serviços Web internos seja substituído porque esse servidor não pode ter o balanceamento de carga.

  - Se você tiver um balanceador de carga de hardware em seu ambiente que você usa para tráfego da Web e SIP internos, o construtor de topologias não pode fazer a distinção.
    
    Os FQDNs do serviço Web devem ser facilmente diferenciados um do outro; Isso ajuda a garantir que o redirecionamento de URL aponte para os clientes em direção ao servidor apropriado. Por exemplo, se você tiver dois FQDNs, talvez considere nomear um meeting.contoso.com e o outro conferencing.contoso.com. Você pode potencialmente executar problemas de redirecionamento se tiver FQDNs com nomes mais semelhantes, como meet1.contoso.com e meet2.contoso.com.

Os serviços Web externos funcionam em conjunto com um proxy reverso na rede de perímetro. Ele fornece aos clientes acesso externo ao uso desses serviços Web. Os FQDNs configurados aqui são enviados para os clientes quando eles fazem logon e são usados para fazer uma conexão HTTPS de volta ao proxy inverso quando se conecta remotamente. O servidor de proxy reverso encaminha o FQDN do serviço Web externo para um balanceador de carga de hardware interno ou diretamente para o pool. O proxy reverso deve ser capaz de resolver o FQDN dos serviços Web externos para o endereço IP do servidor Web interno. O FDQN de serviços Web externos deve ser resolvível na Internet pública.

Se o seu servidor interno for um servidor de edição padrão, o FQDN interno será o FQDN do servidor Standard Edition. Se o seu servidor interno for um pool de front-ends, o FQDN será um VIP (IP virtual) do balanceador de carga de hardware que carrega o balanceamento de servidores internos de Web farm. Um balanceador de carga de hardware é necessário em um pool de front-ends com mais de um servidor Enterprise Edition. Um balanceador de carga não é necessário para um servidor Standard Edition ou um servidor front-end da Enterprise Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

