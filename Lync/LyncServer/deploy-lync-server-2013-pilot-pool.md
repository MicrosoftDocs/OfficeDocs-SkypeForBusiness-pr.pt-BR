---
title: Implantar o pool piloto do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cbb620a4846b05c7f81ecea4d5cc525c9c16c0c1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Implantar o pool piloto do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-22_

Uma das primeiras etapas necessárias para a migração para o Lync Server 2013 é implantar um pool piloto. O pool piloto é onde você testar a coexistência do Lync Server 2013 com sua implantação do Lync Server 2010. A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Lync Server 2013.

Ao implantar um pool piloto, você usa o Assistente Definir novo pool de front-ends. Você deve implantar os mesmos recursos e cargas de trabalho no pool piloto do Lync Server 2013 que você tem no pool do Lync Server 2010. Se você implantou o servidor de arquivamento, o Monitoring Server ou o System Center Operations Manager para arquivamento ou monitoramento do seu ambiente do Lync Server 2010 e deseja continuar o arquivamento ou monitoramento durante a migração, também é necessário implantar esses recursos no seu ambiente piloto. A versão que você implantou para arquivar ou monitorar seu ambiente do Lync Server 2010 não capturará dados no seu ambiente do Lync Server 2013.

<div>


> [!NOTE]  
> O procedimento a seguir discute os recursos e configurações que você deve considerar como parte do processo de implantação do pool piloto. Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto. Para obter etapas detalhadas, consulte o guia de implantação do <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 de implantação</A> .



</div>

**Para implantar um pool piloto do Lync Server 2013**

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Expanda a árvore até atingir **pools de front-ends**do **Lync Server 2013** Enterprise Edition.

3.  Clique com o botão direito em **Pools de front end do Enterprise Edition**, e selecione **Novo pool de front end**.
    
    ![Submenu seleção do pool de servidores do construtor de topologia](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "Submenu seleção do pool de servidores do construtor de topologia")

4.  Insira FQDN do pool. Ao definir o pool piloto, você pode optar por implantar um pool de front-ends Enterprise Edition ou um servidor Standard Edition. O Lync Server 2013 não exige que os recursos do pool piloto correspondam ao que foi implantado em seu pool herdado.
    
    <div>
    

    > [!WARNING]  
    > O pool ou o FQDN definido para seu pool piloto deve ser exclusivo. Ele não pode corresponder ao nome do pool do Lync Server 2010 atualmente implantado ou de qualquer outro servidor atualmente implantado.

    
    </div>
    
    ![Página Definir FQDN do assistente de novo pool de front-ends](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "Página Definir FQDN do assistente de novo pool de front-ends")

5.  Na página **Selecionar recursos**, marque as caixas de seleção para os recursos que você deseja neste pool de Front-Ends. Por exemplo, se estiver implantando apenas mensagens instantâneas e recursos de presença, você deve selecionar a caixa de seleção Conferência para permitir as mensagens instantâneas com vários participantes, mas não marca as caixas de seleção Conferência discada (PSTN), Enterprise Voice ou Controle de Admissão de Chamadas, porque estas representam voz, vídeo e recursos de conferência colaborativos. Para obter informações adicionais sobre como selecionar recursos, consulte [define and configure a front end pool or Standard Edition Server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) na documentação de implantação.
    
    ![Página de seleção de recursos do pool de front-ends](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de seleção de recursos do pool de front-ends")

6.  Na página **selecionar funções de servidor posicionadas** , recomendamos colocar o servidor de mediação no Lync Server 2013. Ao mesclar uma topologia herdada com o Lync Server 2013, exigimos que você primeiro coloque o servidor de mediação do Lync Server 2010. Após mesclar as topologias e configurar o servidor de mediação do Lync Server 2013, você pode decidir se deseja manter o servidor de mediação posicionado ou alterá-lo para um servidor autônomo quando mover a função de servidor de mediação para o Lync Server 2013 mais tarde na implantação -.
    
    ![Página de funções de servidor do pool de front-ends selecionar](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página de funções de servidor do pool de front-ends selecionar")

7.  Na página **Associar Funções de Servidor com este Pool de Front End**, durante a implantação do pool piloto, não escolha a opção **Habilitar um pool de Borda a ser usado pelo componente de mídia deste pool de front-end**. Esse recurso será ativado e colocado online em uma fase posterior da migração. Mantenha essa configuração desmarcada por enquanto.
    
    ![Página associar funções de servidor com pool de front-ends](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página associar funções de servidor com pool de front-ends")

8.  Na página**Selecione um servidor dos aplicativos web do Office**, clique em **Novo**, e especifique o FQDN do servidor de aplicativos.
    
    ![Definir novas propriedades de FQDN do servidor do Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir novas propriedades de FQDN do servidor do Office Web Apps")

9.  Na página **definir o repositório de arquivamento do SQL Server** , ao definir o repositório do SQL Server para o arquivamento e o monitoramento do Lync Server, selecione a instância do SQL Server criada anteriormente para o lync Server 2013.
    
    ![Página Definir repositório do SQL Server de arquivamento](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Página Definir repositório do SQL Server de arquivamento")

10. Para publicar sua topologia, clique com o botão direito no nó do **Lync Server** e clique em **Publicar topologia**.
    
    ![Construtor de topologia exibindo uma topologia configurada](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "Construtor de topologia exibindo uma topologia configurada")

11. Quando o processo de publicação for concluído, clique em **Finalizar**.

Para instalar uma cópia local do repositório de configuração e iniciar os serviços necessários, consulte [setting up front end Servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) na documentação de implantação.


</div>

<span> </span>

</div>

</div>

</div>

