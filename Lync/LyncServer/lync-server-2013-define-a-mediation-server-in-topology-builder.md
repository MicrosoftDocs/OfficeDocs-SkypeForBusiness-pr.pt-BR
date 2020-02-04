---
title: 'Lync Server 2013: definir um servidor de mediação no construtor de topologias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a Mediation Server in Topology Builder
ms:assetid: 59d8f5ba-5064-4ea5-b4bf-2b9736e0fedd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398391(v=OCS.15)
ms:contentKeyID: 48184217
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bdff7da86bd7298511ea0ef384b2736a47882a03
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Definir um servidor de mediação no construtor de topologias no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-25_

Siga as etapas deste tópico para usar o construtor de topologias para definir um servidor de mediação autônomo ou um pool posicionado com um pool de front-ends em um site para o qual você não tenha implantado anteriormente no Enterprise Voice.

Você pode definir uma topologia usando uma conta que seja membro do grupo Administradores.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>Definir o servidor de mediação posicionado em um pool de front-ends

Siga as etapas neste tópico para usar o construtor de topologias para definir um servidor de mediação posicionado em um pool de front-end em um site em que o Enterprise Voice não foi implantado anteriormente.

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para adicionar um servidor de mediação a um pool de front-ends

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  No construtor de topologias, na árvore de console, expanda o nome do site para o qual você deseja definir um pool de front-ends.

3.  Na árvore do console, clique com o botão direito do mouse no tipo de pool de front-end desejado e, em seguida, clique em **novo pool de front-ends..**.

4.  Navegue pelo assistente **Definir Novo Pool de Front-Ends** até chegar à página **Selecionar funções de servidor colocadas**.

5.  Em **selecionar funções de servidor posicionadas**, marque a opção **posicionar servidor de mediação**.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Se o tipo de pool de front-end selecionado for a edição Enterprise, o componente servidor de mediação será instalado em todos os servidores front-end desse pool de front-ends.</P>
    > <LI>
    > <P>O <STRONG>próximo pool de saltos</STRONG> usado pelo servidor de mediação será o pool de front-ends em que o servidor de mediação está posicionado.</P>
    > <LI>
    > <P>O <STRONG>pool de bordas</STRONG> usado pelo servidor de mediação será o mesmo pool de bordas associado ao pool de front-ends em que o servidor de mediação está posicionado.</P></LI></UL>

    
    </div>

6.  Clique em **criar padrão** para usar este pool de front-end para direcionar chamadas do Microsoft Office Communications Server 2007 R2 para a PSTN.

7.  Clique em **concluir** quando terminar de associar um ou mais pares ao pool de front-ends.
    
    <div>
    

    > [!NOTE]  
    > Antes de prosseguir para a próxima etapa no processo de implantação do Enterprise Voice, verifique se o pool do servidor de mediação (ou seja, o pool do front-end com o componente do servidor de mediação está posicionado) está usando os FQDNs que você especificou.

    
    </div>

8.  Em seguida, siga os procedimentos em [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação do guia de implantação para adicionar o servidor de mediação à sua topologia antes de prosseguir para a próxima etapa de modificação das portas de escuta do servidor de mediação, se necessário. Você deve publicar sua topologia toda vez que usar o construtor de topologias para definir ou modificar sua topologia.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>Definir servidor de mediação autônomo

Siga as etapas deste tópico para usar o construtor de topologias a fim de definir um servidor ou pool autônomo de mediação em um site em que o Enterprise Voice não foi implantado anteriormente.

Se você já implantou servidores de mediação posicionados em pools front-ends neste site, ignore esta seção e [Instale os arquivos do servidor de mediação no Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) antes de prosseguir com a [configuração de troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> Esta seção pressupõe que você já tenha configurado pelo menos um pool de front-end, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir e configurar um pool de front-end ou um servidor Standard Edition no Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publicar a topologia no Lync Server 2013</A> na documentação do guia de implantação.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>Para adicionar um servidor de mediação

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  No construtor de topologias, na árvore de console, expanda o nome do site para o qual você deseja definir um servidor de mediação.

3.  Na árvore de console, clique com o botão direito do mouse no nó de **pools de mediação** e clique em **pool do servidor de mediação**.

4.  Em **definir novo pool de mediação**, digite o nome de domínio totalmente qualificado (FQDN) do pool do servidor de mediação.

5.  Em seguida, siga um destes procedimentos:
    
      - Se você quiser implantar vários servidores de mediação no pool para fornecer alta disponibilidade, selecione **vários pools de computadores**.
        
        <div>
        

        > [!NOTE]  
        > Você deve implantar o balanceamento de carga de DNS para dar suporte a pools do servidor de mediação com vários servidores de mediação. Para obter detalhes, consulte a seção usando o balanceamento de carga de DNS na seção de pools do servidor de mediação do <A href="lync-server-2013-dns-load-balancing.md">balanceamento de carga de DNS no Lync Server 2013</A> na documentação de planejamento.

        
        </div>
    
      - Se você quiser implantar apenas um servidor de mediação no pool porque não requer alta disponibilidade, selecione um **único pool de computador**. Ignore a etapa seguinte.

6.  Se você selecionou **Pool de Vários Computadores** na etapa anterior, no item **Definir os computadores neste pool**, clique em **FQDN do Computador**, digite o FQDN de cada servidor no pool e clique em **Adicionar**. Repita esta etapa para todos os outros servidores de mediação que você deseja adicionar ao pool. Quando tiver definido todos os computadores no pool, clique em **Avançar**.

7.  Na página **selecionar o próximo salto** , clique em **próximo pool de saltos**, clique no FQDN do pool de front-ends que usará esse pool do servidor de mediação e, em seguida, clique em **Avançar**.

8.  Na página **Selecionar um Servidor de Borda**, execute um destes procedimentos:
    
      - Se você quiser fornecer conectividade PSTN a usuários externos habilitados para o Enterprise Voice, em **Selecione o pool de bordas usado por esse servidor de mediação**, clique no FQDN do pool do servidor de borda que usará esse pool de servidores de mediação para fornecer conectividade PSTN a esses usuários externos e clique em **Avançar**.
    
      - Se você não planeja habilitar usuários externos para o Enterprise Voice ou se não quiser fornecer conectividade PSTN aos usuários quando eles estiverem fora da rede interna, clique em **Avançar**.

9.  Em seguida, siga os procedimentos em [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação de implantação para adicionar o servidor de mediação à topologia. Você deve publicar sua topologia toda vez que usar o construtor de topologias para criar ou modificar sua topologia, de modo que os dados possam ser usados para instalar os arquivos para os servidores que executam o Lync Server. Em seguida, prossiga para as próximas etapas para modificar as portas de escuta no servidor de mediação, se necessário.

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>Definir as portas de escuta do servidor de mediação

Siga as etapas deste tópico para usar o construtor de topologias a fim de definir as portas de escuta que um servidor ou um pool de mediação aceitará conexões de entrada de um ponto de gateway.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar as portas de escuta do servidor de mediação

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  No construtor de topologias, na árvore de console, expanda o nó de **pools de mediação** e clique com o botão direito do mouse no servidor de mediação anteriormente criado.

3.  Por padrão, as portas ouvidas SIP no servidor de mediação são 5070 para tráfego TLS do Lync Server, 5067 para tráfego TLS de pares (gateways, PBXes ou SBCs). A porta TCP é desabilitada por padrão. Você deve habilitar a porta TCP se tiver gateways que não oferecem suporte a TLS.

4.  Especificar o intervalo de portas de escuta de TLS ou TCP desejadas o servidor de mediação aceitará conexões de entrada de gateways PSTN.
    
    <div>
    

    > [!NOTE]  
    > Não é necessário inserir um intervalo de portas TCP se a opção <STRONG>Habilitar porta TCP</STRONG> não estiver marcada. Essa configuração é opcional.

    
    </div>

Em seguida, [defina um gateway no construtor de topologias no Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) e instale os arquivos em cada servidor de mediação no pool, seguindo os procedimentos em [instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

