---
title: 'Lync Server 2013: alterar a URL dos serviços Web'
description: 'Lync Server 2013: alterar a URL dos serviços Web.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Change the Web Services URL
ms:assetid: 4cee37c0-3b99-4207-997f-bf4229d760c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520992(v=OCS.15)
ms:contentKeyID: 48184063
ms.date: 11/16/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78a7a9b70d475aa952a43d215a8e5cd2068911e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576347"
---
# <a name="change-the-web-services-url-in-lync-server-2013"></a>Alterar a URL de serviços Web no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2015-11-16_

Ao configurar os pools de Front-Ends e os servidores Standard Edition, você tem a opção de configurar um FQDN (nome de domínio totalmente qualificado) de Web farm externo e as portas associadas. Se você não configurou esta URL quando executou o assistente de implantação do Lync Server, precisará definir manualmente essas configurações. Um administrador normalmente não precisa alterar essas configurações, pois essas são as portas recomendadas e padrão.

<div>


> [!NOTE]  
> A captura de tela a seguir foi feita durante a configuração de um servidor Standard Edition, portanto, a opção substituir FQDN está desabilitada. Essa opção é habilitada ao configurar um servidor Enterprise Edition em um pool de front-ends.



</div>

![Editar configurações do pool de serviços Web](images/Gg520992.fbdf5cc9-479a-463f-bb1d-53575ecdfc9d(OCS.15).jpg "Editar configurações do pool de serviços Web")

<div>

## <a name="to-configure-web-services"></a>Para configurar serviços Web

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

3.  No construtor de topologias, na árvore de console em **servidores front-end Standard Edition**, **pools de front-ends Enterprise Edition**e **pools de diretório**, selecione o nome do pool. Clique com o botão direito do mouse no nome, clique em **Editar Propriedades** e em **Serviços Web**.

4.  Adicione ou edite o **FQDN de Serviços Web Externos** e clique em **OK**.
    
    <div>
    

    > [!WARNING]  
    > Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN de serviços Web externos deverá ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-ends ou servidor front-end. Se você também estiver implantando diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deverá ser exclusivo de qualquer outro diretor ou pool de diretores, bem como de qualquer pool de front-ends ou servidor front-end.

    
    </div>

5.  Verifique se as portas de escuta e publicadas estão configuradas corretamente para seu ambiente.

6.  Repita estas etapas para todos os servidores Standard Edition, Pools de Front-Ends e pools de Diretores em seu ambiente.

7.  Na árvore de console, clique em **Lync Server 2013** e, no painel **Ações** clique em **Publicar Topologia**.

Existem alguns requisitos que você deve estar ciente ao configurar as portas de Escuta e Publicação:

  - As portas de escuta mostradas são as portas configuradas para o IIS (Internet Information Server) em cada Servidor Front-End.

  - As portas de escuta internas e externas devem ser diferentes para o IIS. Para as portas de escuta externas, geralmente são iguais porque uma representa o balanceador de carga de hardware para tráfego da Web interno e a outra representa o servidor proxy inverso para tráfego da Web externo.

  - Você pode substituir os serviços Web internos em um pool de front-ends, diretor ou um pool de diretor e definir seu próprio FQDN.
    
    <div>
    

    > [!WARNING]  
    > Se você decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.

    
    </div>

  - As portas publicadas devem ser configuradas no balanceador de carga de hardware ou de proxy reverso como portas de escuta.

  - Para um pool de Front-End (não mostrado no exemplo), o FQDN do pool SIP interno deve ser diferente do FQDN de serviços Web internos, pois o tráfego da Web passa pelo balanceador de carga de hardware e o tráfego de pool SIP interno passa pelo balanceador de carga de DNS. Este requisito deve ser atendido.

  - Uma implantação do Lync Server Standard Edition não precisa ou permite que um FQDN de serviços Web internos seja substituído porque esse servidor não pode ser carregado com balanceamento de carga.

  - Se você tiver um balanceador de carga de hardware no seu ambiente que você usa para o SIP interno e o tráfego da Web, o construtor de topologias não poderá fazer distinção.
    
    Os FQDNs do serviço Web devem ser facilmente diferenciados uns dos outros; Isso ajuda a garantir que o redirecionamento de URL aponte para os clientes em direção ao servidor apropriado. Por exemplo, se você tiver dois FQDNs, poderá considerar o nome de um meeting.contoso.com e o outro conferencing.contoso.com. Você pode potencialmente executar problemas de redirecionamento se tiver FQDNs com nomes mais semelhantes, como meet1.contoso.com e meet2.contoso.com.

Os serviços Web externos funcionam em conjunto com um proxy reverso na rede de perímetro. Ele fornece aos clientes acesso externo ao usando esses serviços Web. Os FQDNs configurados aqui são enviados aos clientes quando eles fazem logon e são usados para estabelecer uma conexão HTTPS com o proxy reverso ao conectar remotamente. O servidor proxy reverso encaminha o FQDN do serviço Web externo para um balanceador de carga de hardware interno ou diretamente para o pool. O proxy reverso deve ser capaz de resolver o FQDN de serviços Web externos para o endereço IP do servidor Web interno. O FQDN de serviços Web externos deve ser resolvido na Internet pública.

Se o seu servidor interno for um servidor Standard Edition, o FQDN interno será o FQDN do servidor Standard Edition. Se seu servidor interno for um pool de Front-End, o FQDN será um VIP (IP virtual) do balanceador de carga de hardware que faz o balanceamento de carga dos servidores de Web farm IP virtual (VIP) que o equilíbrio de carga de servidores de web farm internos. É necessário um balanceador de carga de hardware em um pool de Front-End com mais de um servidor Enterprise Edition. Um balanceador de carga não é necessário para um servidor Standard Edition ou um único Servidor Front-End Enterprise Edition.

</div>

</div>

<span> </span>

</div>

</div>

</div>

