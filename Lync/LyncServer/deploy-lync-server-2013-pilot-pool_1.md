---
title: Implantar o pool piloto do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3df30b2aa45fe9519d724f904e8b375bed794042
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502948"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a>Implantar o pool piloto do Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-22_

Uma das primeiras etapas necessárias para a migração para o Lync Server 2013 é implantar um pool piloto. O pool piloto é onde você testar a coexistência do Lync Server 2013 com a implantação do Office Communications Server 2007 R2. A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Lync Server 2013.

Ao implantar um pool piloto, você usa o Assistente Definir novo pool de front-ends. Você deve implantar os mesmos recursos e cargas de trabalho no pool piloto do Lync Server 2013 que você tem no pool do Office Communications Server 2007 R2. Se você implantou o servidor de arquivamento, o Monitoring Server ou o System Center Operations Manager para arquivamento ou monitoramento do seu ambiente do Office Communications Server 2007 R2 e deseja continuar o arquivamento ou monitoramento durante a migração, também é necessário implantar esses recursos no seu ambiente piloto. A versão implantada para arquivar ou monitorar o ambiente do Office Communications Server 2007 R2 não capturará dados no seu ambiente do Lync Server 2013.

<div>


> [!NOTE]  
> O procedimento a seguir discute os recursos e configurações que você deve considerar como parte do processo de implantação do pool piloto. Esta seção destaca somente os principais pontos que você deve considerar como parte da implantação do pool piloto. Para obter etapas detalhadas, consulte o guia de implantação do <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 de implantação</A> .



</div>

**Para implantar um pool piloto do Lync Server 2013**

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Abra o Construtor de Topologia e selecione criar uma nova topologia.

3.  Insira o domínio SIP primário.
    
    ![Criar nova topologia, definir página de domínio primário](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Criar nova topologia, definir página de domínio primário")

4.  Continue completando o assistente até que chegue no assistente **Assistente Definir o novo pool de Front-Ends**. Clique em Próximo.

5.  Insira o FQDN do pool. Ao definir o pool piloto, você pode optar por implantar um pool de front-ends Enterprise Edition ou um servidor Standard Edition. O Lync Server 2013 não exige que os recursos do pool piloto correspondam ao que foi implantado em seu pool herdado.
    
    <div>
    

    > [!WARNING]  
    > O pool ou o FQDN definido para seu pool piloto deve ser exclusivo. Ele não pode corresponder ao nome do pool do Office Communications Server 2007 R2 atualmente implantado ou de qualquer outro servidor atualmente implantado.

    
    </div>
    
    ![Definir a página FQDN do pool de front-ends](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definir a página FQDN do pool de front-ends")

6.  Defina o computador que será adicionado ao pool.
    
    ![Caixa de diálogo Definir novo pool de front-ends](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Caixa de diálogo Definir novo pool de front-ends")

7.  Na página **Selecionar recursos**, marque as caixas de seleção para os recursos que você deseja neste pool de Front-Ends. Por exemplo, se estiver implantando apenas mensagens instantâneas e recursos de presença, você deve selecionar a caixa de seleção Conferência para permitir as mensagens instantâneas com vários participantes, mas não marca as caixas de seleção Conferência discada (PSTN), Enterprise Voice ou Controle de Admissão de Chamadas, porque estas representam voz, vídeo e recursos de conferência colaborativos. Para obter informações adicionais sobre como selecionar recursos, consulte [define and configure a front end pool or Standard Edition Server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) na documentação de implantação.
    
    ![Página de seleção de recursos do pool de front-ends](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de seleção de recursos do pool de front-ends")

8.  Na página **selecionar funções de servidor posicionadas** , recomendamos colocar o servidor de mediação no Lync Server 2013. Ao mesclar uma topologia herdada com o Lync Server 2013, exige que você primeiro coloque o servidor de mediação do Office Communications Server 2007 R2. Após mesclar as topologias e configurar o servidor de mediação do Lync Server 2013, você pode decidir se deseja manter o servidor de mediação colocado ou alterá-lo para um servidor autônomo quando mover a função de servidor de mediação para o Lync Server 2013 mais tarde no processo de implantação.
    
    ![Página de funções de servidor do pool de front-ends selecionar](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Página de funções de servidor do pool de front-ends selecionar")

9.  Na página **Associar Funções de Servidor com este Pool de Front End**, durante a implantação do pool piloto, não escolha a opção **Habilitar um pool de Borda a ser usado pelo componente de mídia deste pool de front-end**. Esse recurso será ativado e colocado online em uma fase posterior da migração. Mantenha essa configuração desmarcada por enquanto.
    
    ![Página associar funções de servidor com pool de front-ends](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Página associar funções de servidor com pool de front-ends")

10. Na página**Selecione um servidor dos aplicativos web do Office**, clique em **Novo**, e especifique o FQDN do servidor de aplicativos.
    
    ![Definir novas propriedades de FQDN do servidor do Office Web Apps](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir novas propriedades de FQDN do servidor do Office Web Apps")

11. Na página **definir o repositório de arquivamento do SQL Server** , selecione a instância do SQL Server criada anteriormente para o Lync Server 2013.
    
    ![Página Definir repositório do SQL Server de arquivamento](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Página Definir repositório do SQL Server de arquivamento")

12. Na página **definir o repositório do SQL Server de monitoramento** , selecione a instância do SQL Server criada anteriormente para o Lync Server 2013. Clique em **Concluir**.

13. A partir do nó do topo do Construtor de Topologia, clique com o botão direito em **Lync Server** e clique em **Editar Propriedades.** Clique em **URLs simples**.

14. Atualize a **URL de acesso administrativo**.
    
    ![Editar propriedades, página de URLs simples](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Editar propriedades, página de URLs simples")
    
    Para obter informações adicionais sobre URLs simples, consulte o tópico [Editar ou configurar URLs simples no Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) na documentação de implantação.

15. A partir de **Editar Propriedades**, clique em **Servidor de Gerenciamento Central**.

16. Na lista suspensa, selecione o pool do Lync Server 2013.
    
    ![Página Editar propriedades, servidor de gerenciamento central](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Página Editar propriedades, servidor de gerenciamento central")

17. Clique em OK para fechar a página**Editar Propriedades**.

18. A partir do menu **Ação**, selecione **Publicar Topologia**.

19. Quando o processo de publicação for concluído, clique em **Finalizar**.

20. Retornando ao assistente de implantação do Lync Server 2013, clique em **instalar ou atualizar o sistema do Lync Server**.
    
    ![Assistente de implantação do Lync Server 2013](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Assistente de implantação do Lync Server 2013")

Para instalar uma cópia local do repositório de configuração e iniciar os serviços necessários, consulte [setting up front end Servers and front end pools for Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) na documentação de implantação.


</div>

<span> </span>

</div>

</div>

</div>

