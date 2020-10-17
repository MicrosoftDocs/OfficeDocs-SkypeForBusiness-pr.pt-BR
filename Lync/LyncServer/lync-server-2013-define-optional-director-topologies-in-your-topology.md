---
title: 'Lync Server 2013: definir topologias opcionais de diretor em sua topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define optional Director topologies in your topology
ms:assetid: 8e9a659d-23b0-401d-b296-59c7df414d49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398717(v=OCS.15)
ms:contentKeyID: 48184808
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e53512d2d3c0bd99c4d5b23d20f21859ec974415
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504568"
---
# <a name="define-optional-director-topologies-in-your-topology-for-lync-server-2013"></a>Definir topologias opcionais de diretor em sua topologia para o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-08_

Os diretores do Lync Server 2013 podem ser servidores de instância única ou podem ser instalados como um pool de balanceamento de carga de vários diretores para maior disponibilidade e capacidade. O balanceamento de carga de hardware e o balanceamento de carga do DNS (sistema de nomes de domínio) são suportados. Este tópico explica como configurar o balanceamento de carga de DNS para pools de diretores.

Para publicar, habilitar ou desabilitar uma topologia com êxito ao adicionar ou remover uma função de servidor, você deve estar conectado como um usuário que seja membro dos grupos **RTCUniversalServerAdmins** e **Domain admins** . Você também pode delegar os direitos e permissões de administrador adequados para a adição de funções de servidor. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md) na documentação de implantação do servidor Standard Edition ou Enterprise Edition. Para outras alterações de configuração, somente a associação ao grupo **RTCUniversalServerAdmins** é necessária.

Este tópico descreve as etapas para definir e publicar a topologia para as duas topologias de Diretor:

  - Para definir o diretor (instância única)

  - Para definir o Diretor (pool de vários Diretores)

<div>

## <a name="to-define-the-director-single-instance"></a>Para definir o diretor (instância única)

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Na página de boas-vindas, clique em **Baixar Topologia da Implantação Existente**.

3.  Na caixa de diálogo **Salvar Topologia Como**, digite o nome o local da cópia local da topologia existente e clique em **Salvar**.

4.  Expanda o site no qual você planeja adicionar o Diretor, clique com o botão direito do mouse em **Pools de Diretores** e clique em **Novo Pool de Diretores**.

5.  Na caixa de diálogo **Definir o FQDN do pool de Diretores**, faça o seguinte:
    
      - Em **FQDN do Pool**, digite o FQDN do pool de Diretores.
    
      - Clique em **Pool de computador único** e em **Avançar**.

6.  Na caixa de diálogo **Definir o compartilhamento de arquivo**, siga um destes procedimentos:
    
    1.  Para usar um compartilhamento de arquivo existente, clique em **Usar um compartilhamento de arquivos previamente definido**, selecione um compartilhamento de arquivo na lista e clique em **Avançar**.
    
    2.  Para criar um novo compartilhamento de arquivo, clique em **Definir um novo compartilhamento de arquivo**, digite o FQDN do local do compartilhamento de arquivo em **FQDN do servidor de arquivos**, digite o nome do compartilhamento em **Compartilhamento de Arquivo** e clique em **Avançar**.
    
    <div>
    

    > [!IMPORTANT]  
    > O compartilhamento de arquivo especificado ou criado nesta etapa precisa existir ou ser criado antes da publicação da topologia.<BR>O compartilhamento de arquivo atribuído a um Diretor não é realmente usado. Dessa forma, você pode atribuir o compartilhamento de arquivo de qualquer pool na organização.

    
    </div>

7.  Na caixa de diálogo **Especificar a URL dos Serviços Web**, em **URL Base Externa**, especifique o FQDN para os Diretores e clique em **Concluir**.
    
    <div>
    

    > [!IMPORTANT]  
    > O nome deve ser resolvido a partir de servidores DNS da Internet e apontar para o endereço IP público do proxy reverso, que escuta solicitações HTTP/HTTPS para essa URL e as proxies para o diretório virtual de serviços Web externos nesse diretor.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN de serviços Web externos deverá ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-ends ou servidor front-end. Se você também estiver implantando diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deverá ser exclusivo de qualquer outro diretor ou pool de diretores, bem como de qualquer pool de front-ends ou servidor front-end. Se decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.

    
    </div>

8.  Publique a topologia.

</div>

<div>

## <a name="to-define-the-director-multiple-director-pool"></a>Para definir o Diretor (pool de vários Diretores)

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Na página de boas-vindas, clique em **Baixar Topologia da Implantação Existente**.

3.  Na caixa de diálogo **Salvar Topologia Como**, digite o nome o local da cópia local da topologia existente e clique em **Salvar**.

4.  Expanda o site no qual você planeja adicionar o Diretor, clique com o botão direito do mouse em **Pools de Diretores** e clique em **Novo Pool de Diretores**.

5.  Na caixa de diálogo **Definir o FQDN do pool de Diretores**, faça o seguinte:
    
      - Em **FQDN do Pool**, digite o FQDN do pool de Diretores.
    
      - Clique em **Pool de vários computadores** e, em seguida, clique em **Avançar**.

6.  Na caixa de diálogo **Definir os computadores neste pool**, faça o seguinte:
    
      - Especifique o FQDN do computador do primeiro membro do pool e clique em **Adicionar**.
    
      - Repita a etapa anterior para cada computador que você deseja adicionar. Quando terminar, clique em **Avançar**.

7.  Na caixa de diálogo **Definir o compartilhamento de arquivo**, siga um destes procedimentos:
    
      - Para usar um compartilhamento de arquivo existente, clique em **Usar um compartilhamento de arquivos previamente definido**, selecione um compartilhamento de arquivo na lista e clique em **Avançar**.
    
      - Para criar um novo compartilhamento de arquivo, clique em **Definir um novo compartilhamento de arquivo**, digite o FQDN do local do compartilhamento de arquivo em **FQDN do servidor de arquivos**, digite o nome do compartilhamento em **Compartilhamento de Arquivo** e clique em **Avançar**.
    
    <div>
    

    > [!IMPORTANT]  
    > O compartilhamento de arquivo especificado ou criado nesta etapa precisa existir ou ser criado antes da publicação da topologia.<BR>O compartilhamento de arquivo atribuído a um Diretor não é realmente usado. Dessa forma, você pode atribuir o compartilhamento de arquivo de qualquer pool na organização.

    
    </div>

8.  Na caixa de diálogo **Especificar a URL dos Serviços Web**, em **URL Base Externa**, especifique o FQDN para os Diretores e clique em **Concluir**.
    
    <div>
    

    > [!IMPORTANT]  
    > O nome precisa ser resolvido a partir dos servidores DNS de Internet e apontar para o endereço IP público do proxy reverso, que escuta as solicitações HTTP/HTTPS enviadas a essa URL e as atribui ao diretório virtual dos Serviços Web nesse pool de Diretores.

    
    </div>
    
    <div>
    

    > [!WARNING]  
    > Se você tiver mais de um pool de front-ends ou servidor front-end, o FQDN de serviços Web externos deverá ser exclusivo. Por exemplo, se você definir o FQDN de serviços Web externos de um servidor front-end como <STRONG>pool01.contoso.com</STRONG>, não será possível usar o <STRONG>pool01.contoso.com</STRONG> para outro pool de front-ends ou servidor front-end. Se você também estiver implantando diretores, o FQDN de serviços Web externos definido para qualquer diretor ou pool de diretores deverá ser exclusivo de qualquer outro diretor ou pool de diretores, bem como de qualquer pool de front-ends ou servidor front-end. Se decidir substituir os serviços Web internos por um FQDN autodefinido, cada FQDN deverá ser exclusivo de qualquer outro pool de front-ends, diretor ou um pool de diretores.

    
    </div>

9.  Publique a topologia.

</div>

</div>

<span> </span>

</div>

</div>

</div>

