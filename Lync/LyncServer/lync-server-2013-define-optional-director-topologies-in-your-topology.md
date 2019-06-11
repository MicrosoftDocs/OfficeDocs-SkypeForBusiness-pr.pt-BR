---
title: 'Lync Server 2013: Definir topologias opcionais de Diretor em sua topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 524259226b44d68367b631c2b7cef5513e0770e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829716"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Definir topologias opcionais de Diretor em sua topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-08_

Os directors do Lync Server 2013 podem ser servidores de instância única ou podem ser instalados como um pool de balanceamento de carga de vários directors para maior disponibilidade e capacidade. Há suporte para o balanceamento de carga de hardware e o balanceamento de carga de DNS (sistema de nomes de domínio). Este tópico explica como configurar o balanceamento de carga de DNS para pools de directors.

Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que é membro do grupo **RTCUniversalServerAdmins** e **Administradores do domínio** . Você também pode delegar direitos e permissões de administrador adequadas para adicionar funções de servidor. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition Server. Para outras alterações de configuração, somente a associação no grupo **RTCUniversalServerAdmins** é necessária.

Este tópico descreve as etapas para definir e publicar a topologia para as duas topologias de Diretor:

  - Para definir o diretor (instância única)

  - Para definir o diretor (pool de vários directors)

<div>

## <a name="to-define-the-director-single-instance"></a>Para definir o diretor (instância única)

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Na página de boas-vindas, clique em **baixar topologia da implantação existente**.

3.  Na caixa de diálogo **salvar topologia como** , digite o nome e o local da cópia local da topologia existente e, em seguida, clique em **salvar**.

4.  Expanda o site no qual você planeja adicionar o diretor, clique com o botão direito do mouse em pools do **diretor**e clique em **novo pool**de directors.

5.  Na caixa de diálogo **definir o FQDN do pool** de directors, faça o seguinte:
    
      - Em **pool FQDN**, digite o FQDN do pool do diretor.
    
      - Clique em **pool de computador único**e, em seguida, clique em **Avançar**.

6.  Na caixa de diálogo **definir o compartilhamento de arquivos** , siga um destes procedimentos:
    
    1.  Para usar um compartilhamento de arquivos existente, clique em **usar um compartilhamento de arquivos definido anteriormente**, selecione um compartilhamento de arquivos na lista e clique em **Avançar**.
    
    2.  Para criar um novo compartilhamento de arquivos, clique em **definir um novo compartilhamento de arquivos**, digite o FQDN para o local do compartilhamento de arquivos no **FQDN do servidor de arquivos**, digite o nome do compartilhamento em compartilhamento de **arquivos**e clique em **Avançar**.
    
    <div>
    

    > [!IMPORTANT]  
    > O compartilhamento de arquivo que você especificar ou criar nesta etapa deve existir ou ser criado antes da publicação da topologia.<BR>O compartilhamento de arquivos atribuído a um diretor não é usado realmente para que você possa atribuir o compartilhamento de arquivos de qualquer pool na organização.

    
    </div>

7.  Na caixa de diálogo **especificar a URL de serviços Web** , em **URL de base externa**, especifique o FQDN para os directors e clique em **concluir**.
    
    <div>
    

    > [!IMPORTANT]  
    > O nome deve ser resolvível em servidores DNS de Internet e apontar para o endereço IP público do proxy reverso, que escuta as solicitações HTTP/HTTPS para essa URL e as proxies para o diretório virtual de serviços Web externos nesse diretor.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Se você tiver mais de um servidor front-end ou servidor front-end, os serviços Web externos FQDN deverão ser exclusivos. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-end ou servidor front-end. Se você também estiver implantando diretores, os serviços Web externos FQDN definidos para qualquer diretor de director ou diretor devem ser exclusivos de qualquer outro diretor ou pool de director, bem como qualquer pool de front-end ou servidor front-end. Se decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.

    
    </div>

8.  Publique a topologia.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>Para definir o diretor (pool de vários directors)

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Na página de boas-vindas, clique em **baixar topologia da implantação existente**.

3.  Na caixa de diálogo **salvar topologia como** , digite o nome e o local da cópia local da topologia existente e, em seguida, clique em **salvar**.

4.  Expanda o site no qual você planeja adicionar o diretor, clique com o botão direito do mouse em pools do **diretor**e clique em **novo pool**de directors.

5.  Na caixa de diálogo **definir o FQDN do pool** de directors, faça o seguinte:
    
      - Em **pool FQDN**, digite o FQDN do pool do diretor.
    
      - Clique em **vários pools de computador**e clique em **Avançar**.

6.  Na caixa de diálogo **definir os computadores neste pool** , faça o seguinte:
    
      - Especifique o FQDN do computador do primeiro membro do pool e clique em **Adicionar**.
    
      - Repita a etapa anterior para cada computador que você deseja adicionar. Quando terminar, clique em **Avançar**.

7.  Na caixa de diálogo **definir o compartilhamento de arquivos** , siga um destes procedimentos:
    
      - Para usar um compartilhamento de arquivos existente, clique em **usar um compartilhamento de arquivos definido anteriormente**, selecione um compartilhamento de arquivos na lista e clique em **Avançar**.
    
      - Para criar um novo compartilhamento de arquivos, clique em **definir um novo compartilhamento de arquivos**, digite o FQDN para o local do compartilhamento de arquivos no **FQDN do servidor de arquivos**, digite o nome do compartilhamento em compartilhamento de **arquivos**e clique em **Avançar**.
    
    <div>
    

    > [!IMPORTANT]  
    > O compartilhamento de arquivo que você especificar ou criar nesta etapa deve existir ou ser criado antes da publicação da topologia.<BR>O compartilhamento de arquivos atribuído a um diretor não é usado realmente para que você possa atribuir o compartilhamento de arquivos de qualquer pool na organização.

    
    </div>

8.  Na caixa de diálogo **especificar a URL de serviços Web** , em **URL de base externa**, especifique o FQDN para os directors e clique em **concluir**.
    
    <div>
    

    > [!IMPORTANT]  
    > O nome deve ser resolvível em servidores DNS de Internet e apontar para o endereço IP público do proxy reverso, que escuta as solicitações HTTP/HTTPS enviadas a essa URL e as proxies para o diretório virtual de serviços Web externos nesse pool de directors.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Se você tiver mais de um servidor front-end ou servidor front-end, os serviços Web externos FQDN deverão ser exclusivos. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-end ou servidor front-end. Se você também estiver implantando diretores, os serviços Web externos FQDN definidos para qualquer diretor de director ou diretor devem ser exclusivos de qualquer outro diretor ou pool de director, bem como qualquer pool de front-end ou servidor front-end. Se decidir substituir os serviços internos da Web por um FQDN autodefinido, cada FQDN deve ser exclusivo de qualquer outro pool de front-end, diretor ou um pool de diretor.

    
    </div>

9.  Publique a topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

