---
title: Implantar o pool piloto do Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5e9068ca3ff5a2827991869598a2066473cc5af
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836837"
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

Uma das primeiras etapas necessárias para a migração para o Lync Server 2013 é implantar um pool piloto. O pool piloto é onde você testa a coexistência do Lync Server 2013 com a implantação do Office Communications Server 2007 R2. A coexistência é um estado temporário que dura até que você tenha movido todos os usuários e pools para o Lync Server 2013.

Ao implantar um pool piloto, use o assistente para definir novo pool de front-end. Você deve implantar os mesmos recursos e cargas de trabalho no pool piloto do Lync Server 2013 que você tem no pool do Office Communications Server 2007 R2. Se você implantou o arquivamento do servidor, o Monitoring Server ou o System Center Operations Manager para arquivar ou monitorar seu ambiente do Office Communications Server 2007 R2 e deseja continuar a arquivar ou monitorar durante a migração, é preciso Além disso, implante esses recursos em seu ambiente piloto. A versão que você implantou para arquivar ou monitorar seu ambiente do Office Communications Server 2007 R2 não capturará dados em seu ambiente do Lync Server 2013.

<div>


> [!NOTE]  
> O procedimento a seguir discute os recursos e configurações que devem ser considerados como parte do processo de implantação do pool piloto geral. Esta seção destaca apenas os pontos-chave que você deve considerar como parte da sua implantação de pool piloto. Para obter etapas detalhadas, consulte o guia de implantação implantando o <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> .



</div>

**Para implantar um pool piloto do Lync Server 2013**

1.  Faça logon no computador no qual o Construtor de Topologias está instalado como um membro do grupo Admins. do Domínio ou do grupo RTCUniversalServerAdmins.

2.  Abra o construtor de topologias e escolha criar uma nova topologia.

3.  Digite o domínio SIP primário.
    
    ![Criar nova topologia, definir página de domínio primário] (images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "Criar nova topologia, definir página de domínio primário")

4.  Continue a preencher o assistente até chegar ao assistente **definir o novo pool de front-end** . Click Next.

5.  Digite o FQDN do pool. Ao definir o pool piloto, você pode optar por implantar um pool de front-end do Enterprise Edition ou um servidor Standard Edition. O Lync Server 2013 não requer que seus recursos de pool piloto correspondam ao que foi implantado em seu pool herdado.
    
    <div>
    

    > [!WARNING]  
    > O nome de domínio totalmente qualificado (FQDN) do pool ou do servidor que você define para o pool piloto deve ser exclusivo. Ele não pode corresponder ao nome do pool do Office Communications Server 2007 R2 atualmente implantado ou de qualquer outro servidor atualmente implantado.

    
    </div>
    
    ![Definir a página de FQDN do pool de front-end] (images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "Definir a página de FQDN do pool de front-end")

6.  Defina o computador que será adicionado ao pool.
    
    ![Caixa de diálogo Definir novo pool de front-end] (images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "Caixa de diálogo Definir novo pool de front-end")

7.  Na página **selecionar recursos** , marque as caixas de seleção dos recursos que você deseja neste pool de front-ends. Por exemplo, se você estiver implantando apenas mensagens instantâneas e recursos de presença, marque a caixa de seleção conferência para permitir mensagens instantâneas com vários participantes, mas não marque as caixas de seleção conferência discada (PSTN), Enterprise Voice ou controle de admissão de chamadas, Porque elas representam recursos de voz, vídeo e conferência colaborativa. Para obter informações adicionais sobre a seleção de recursos, consulte [definir e configurar um servidor front-end ou um servidor Standard Edition no Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) na documentação de implantação.
    
    ![Página de seleção de recursos do pool de front-end] (images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "Página de seleção de recursos do pool de front-end")

8.  Na página **selecionar funções de servidor posicionadas** , recomendamos posicionar o servidor de mediação no Lync Server 2013. Ao mesclar uma topologia herdada com o Lync Server 2013, precisamos primeiro colocar o servidor de mediação do Office Communications Server 2007 R2. Depois de mesclar as topologias e configurar o servidor de mediação do Lync Server 2013, você pode decidir se deseja manter o servidor de mediação posicionado ou alterá-lo para um servidor autônomo ao mover a função do servidor de mediação para o Lync Server 2013 mais tarde na implantação com.
    
    ![Grupo de front-end selecionar página de funções de servidor posicionada] (images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "Grupo de front-end selecionar página de funções de servidor posicionada")

9.  Na página **associar funções de servidor a este pool de front-end** , durante a implantação do pool piloto, não escolha **habilitar um pool de bordas para ser usado pelo componente de mídia dessa opção do pool de front-end** . Este é um recurso que você habilitará e colocará online em uma fase posterior da migração. Mantenha essa configuração desmarcada por enquanto.
    
    ![Associar funções de servidor com a página de pool de front-end] (images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "Associar funções de servidor com a página de pool de front-end")

10. Na página **selecionar um servidor dos Office Web Apps** , clique em **novo**e especifique o FQDN do servidor de aplicativo.
    
    ![Definir novas propriedades de FQDN do servidor do Office Web Apps] (images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "Definir novas propriedades de FQDN do servidor do Office Web Apps")

11. Na página **definir a loja do SQL Server Store** , selecione a instância do SQL Server criada anteriormente para o Lync Server 2013.
    
    ![Página definir o arquivamento da loja do SQL Server] (images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "Página definir o arquivamento da loja do SQL Server")

12. Na página **definir o monitoramento do SQL Server Store** , selecione a instância do SQL Server criada anteriormente para o Lync Server 2013. Clique em **Concluir**.

13. No nó superior do construtor de topologias, clique com o botão direito do mouse no **Lync Server** e clique em **Editar propriedades.** Clique em **URLs simples**.

14. Atualize a **URL de acesso administrativo**.
    
    ![Editar propriedades, página de URLs simples] (images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "Editar propriedades, página de URLs simples")
    
    Para obter informações adicionais sobre URLs simples, consulte o tópico [Editar ou configurar URLs simples no Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) na documentação de implantação.

15. Em **Editar propriedades**, clique em **servidor de gerenciamento central**.

16. Na lista suspensa, selecione o pool do Lync Server 2013.
    
    ![Editar propriedades, página do servidor de gerenciamento central] (images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "Editar propriedades, página do servidor de gerenciamento central")

17. Clique em OK para fechar **a página Editar propriedades** .

18. No menu **ação** , selecione **publicar topologia**.

19. Quando o processo de publicação for concluído, clique em **concluir**.

20. Retornando ao assistente de implantação do Lync Server 2013, clique em **instalar ou atualizar o sistema do Lync Server**.
    
    ![Assistente de implantação do Lync Server 2013] (images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Assistente de implantação do Lync Server 2013")

Para instalar uma cópia local do repositório de configurações e iniciar os serviços necessários, consulte [Configurando servidores front-end e pools front-end para o Lync Server 2013](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) na documentação de implantação.


</div>

<span> </span>

</div>

</div>

</div>

