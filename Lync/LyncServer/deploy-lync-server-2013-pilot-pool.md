---
title: Implantar o pool piloto do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93fb3c5062cc1f817d3de7b869f57600178ad454
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Implantar o pool piloto do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-11-22_

Uma das primeiras etapas necessárias para a migração para o Lync Server 2013 é implantar um pool piloto. O pool piloto é onde você testa a coexistência do Lync Server 2013 com a implantação do Lync Server 2010. A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Lync Server 2013.

Ao implantar um pool piloto, use o assistente para definir novo pool de front-end. Você deve implantar os mesmos recursos e cargas de trabalho no pool piloto do Lync Server 2013 que você tem no pool do Lync Server 2010. Se você implantou o arquivamento do servidor, o Monitoring Server ou o System Center Operations Manager para arquivar ou monitorar seu ambiente do Lync Server 2010 e deseja continuar a arquivar ou monitorar durante a migração, também é necessário implantar esses recursos em seu ambiente piloto. A versão que você implantou para arquivar ou monitorar seu ambiente do Lync Server 2010 não capturará dados em seu ambiente do Lync Server 2013.

<div>


> [!NOTE]  
> O procedimento a seguir discute os recursos e configurações que devem ser considerados como parte do processo de implantação do pool piloto geral. Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto. Para obter etapas detalhadas, consulte o guia de implantação implantando o <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Para implantar um pool piloto do Lync Server 2013**

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Expanda a árvore até acessar os pools de **front-end**do **Lync Server 2013** Enterprise Edition.

3.  Clique com o botão direito do mouse em **pools front end do Enterprise Edition**e selecione **novo pool de front-end**.
    
    ![Submenu de seleção do pool de servidores do construtor de topologia] (images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Submenu de seleção do pool de servidores do construtor de topologia")

4.  Digite o FQDN do pool. Ao definir o pool piloto, você pode optar por implantar um pool de front-end do Enterprise Edition ou um servidor Standard Edition. O Lync Server 2013 não requer que seus recursos de pool piloto correspondam ao que foi implantado em seu pool herdado.
    
    <div>
    

    > [!WARNING]  
    > O nome de domínio totalmente qualificado (FQDN) do pool ou do servidor que você define para o pool piloto deve ser exclusivo. Ele não pode corresponder ao nome do pool do Lync Server 2010 implantado no momento ou a qualquer outro servidor atualmente implantado.

    
    </div>
    
    ![Assistente para definir novo pool de front-ends. página FQDN] (images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Assistente para definir novo pool de front-ends. página FQDN")

5.  Na página **selecionar recursos** , marque as caixas de seleção dos recursos que você deseja neste pool de front-ends. Por exemplo, se você estiver implantando apenas mensagens instantâneas e recursos de presença, marque a caixa de seleção conferência para permitir mensagens instantâneas com vários participantes, mas não marque as caixas de seleção conferência discada (PSTN), Enterprise Voice ou controle de admissão de chamadas, Porque elas representam recursos de voz, vídeo e conferência colaborativa. Para obter informações adicionais sobre a seleção de recursos, consulte [definir e configurar um servidor front-end ou um servidor Standard Edition no Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) na documentação de implantação.
    
    ![Página de seleção de recursos do pool de front-end] (images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de seleção de recursos do pool de front-end")

6.  Na página **selecionar funções de servidor posicionadas** , recomendamos posicionar o servidor de mediação no Lync Server 2013. Ao mesclar uma topologia herdada com o Lync Server 2013, precisamos primeiro colocar o servidor de mediação do Lync Server 2010. Depois de mesclar as topologias e configurar o servidor de mediação do Lync Server 2013, você pode decidir se deseja manter o servidor de mediação posicionado ou alterá-lo para um servidor autônomo ao mover a função do servidor de mediação para o Lync Server 2013 mais tarde na implantação com.
    
    ![Grupo de front-end selecionar página de funções de servidor posicionada] (images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Grupo de front-end selecionar página de funções de servidor posicionada")

7.  Na página **associar funções de servidor a este pool de front-end** , durante a implantação do pool piloto, não escolha **habilitar um pool de bordas para ser usado pelo componente de mídia dessa opção do pool de front-end** . Este é um recurso que você habilitará e colocará online em uma fase posterior da migração. Mantenha essa configuração desmarcada por enquanto.
    
    ![Associar funções de servidor com a página de pool de front-end] (images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associar funções de servidor com a página de pool de front-end")

8.  Na página **selecionar um servidor dos Office Web Apps** , clique em **novo**e especifique o FQDN do servidor de aplicativo.
    
    ![Definir novas propriedades de FQDN do servidor do Office Web Apps] (images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir novas propriedades de FQDN do servidor do Office Web Apps")

9.  Na página **definir a loja do SQL Server Store** , ao definir a loja do SQL Server para o arquivamento e o monitoramento do Lync Server, selecione a instância do SQL Server criada anteriormente para o Lync Server 2013.
    
    ![Página definir o arquivamento da loja do SQL Server] (images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Página definir o arquivamento da loja do SQL Server")

10. Para publicar sua topologia, clique com o botão direito do mouse no nó do **Lync Server** e, em seguida, clique em **publicar topologia**.
    
    ![Construtor de topologias exibindo uma topologia] configurada (images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Construtor de topologias exibindo uma topologia") configurada

11. Quando o processo de publicação for concluído, clique em **concluir**.

Para instalar uma cópia local do repositório de configurações e iniciar os serviços necessários, consulte [Configurando servidores front-end e pools front-end para o Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) na documentação de implantação.


</div>

<span> </span>

</div>

</div>

</div>

