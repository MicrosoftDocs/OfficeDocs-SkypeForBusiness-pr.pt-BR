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
ms.openlocfilehash: b0109a7091870b7409fd9bc20b9de3abd3b2f3a4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138262"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-mediation-server-in-topology-builder-in-lync-server-2013"></a>Definir um servidor de mediação no construtor de topologias no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-03-25_

Siga as etapas deste tópico para usar o construtor de topologias a fim de definir um servidor de mediação autônomo ou um pool colocado com um pool de front-ends em um site para o qual você não tenha implantado o Enterprise Voice.

Você pode definir uma topologia usando uma conta que seja membro do grupo Administradores.

<div>

## <a name="define-mediation-server-collocated-to-a-front-end-pool"></a>Definir o servidor de mediação colocado em um pool de front-ends

Siga as etapas deste tópico para usar o construtor de topologias a fim de definir um servidor de mediação colocado em um pool de front-ends em um site onde o Enterprise Voice não tenha sido implantado anteriormente.

<div>

## <a name="to-add-a-mediation-server-to-a-front-end-pool"></a>Para adicionar um servidor de mediação a um pool de front-ends

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  No construtor de topologias, na árvore de console, expanda o nome do site para o qual você deseja definir um pool de front-ends.

3.  Na árvore do console, clique com o botão direito do mouse no tipo de pool de front-ends desejado e, em seguida, clique em **novo pool de front-ends..**.

4.  Navegue pelo assistente **Definir Novo Pool de Front-Ends** até chegar à página **Selecionar funções de servidor colocadas**.

5.  Em **selecionar funções de servidor**colocadas, marque a opção colocar **servidor de mediação**.
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P>Se o tipo de pool de front-ends selecionado for Enterprise Edition, o componente do servidor de mediação será instalado em todos os servidores front-end desse pool de front-ends.</P>
    > <LI>
    > <P>O <STRONG>pool de próximo salto</STRONG> usado pelo servidor de mediação será o pool de front-ends onde o servidor de mediação é colocado.</P>
    > <LI>
    > <P>O <STRONG>pool de borda</STRONG> usado pelo servidor de mediação será o mesmo pool de borda associado ao pool de front-ends onde o servidor de mediação é colocado.</P></LI></UL>

    
    </div>

6.  Clique em **tornar padrão** para usar este pool de front-ends para rotear chamadas do Microsoft Office Communications Server 2007 R2 para o PSTN.

7.  Clique em **concluir** quando tiver terminado de associar um ou mais pares ao pool de front-ends.
    
    <div>
    

    > [!NOTE]  
    > Antes de prosseguir para a próxima etapa no processo de implantação do Enterprise Voice, verifique se o pool do servidor de mediação (ou seja, pool de front-ends com o componente do servidor de mediação colocado) está usando os FQDNs que você especificou.

    
    </div>

8.  Em seguida, siga os procedimentos em [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação do guia de implantação para adicionar o servidor de mediação à sua topologia antes de prosseguir para a próxima etapa de modificar as portas de escuta do servidor de mediação, se necessário. Você deve publicar sua topologia cada vez que usar o construtor de topologias para definir ou modificar sua topologia.

</div>

</div>

<div>

## <a name="define-stand-alone-mediation-server"></a>Definir servidor de mediação autônomo

Siga as etapas deste tópico para usar o construtor de topologias para definir um servidor de mediação autônomo ou um pool em um site onde o Enterprise Voice não tenha sido implantado anteriormente.

Se você já implantou servidores de mediação colocados em pools de front-ends neste site, pode ignorar esta seção e [instalar os arquivos para o servidor de mediação no Lync server 2013](lync-server-2013-install-the-files-for-mediation-server.md) antes de prosseguir com a [configuração de troncos no Lync Server 2013](lync-server-2013-configuring-trunks.md).

<div>


> [!NOTE]  
> Esta seção pressupõe que você já configurou pelo menos um pool de front-ends, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir e configurar um pool de front-ends ou servidor Standard Edition no Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publicar a topologia no Lync Server 2013</A> na documentação do guia de implantação.



</div>

<div>

## <a name="to-add-a-mediation-server"></a>Para adicionar um Servidor de Mediação

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  No construtor de topologias, na árvore de console, expanda o nome do site para o qual você deseja definir um servidor de mediação.

3.  Na árvore do console, clique com o botão direito do mouse no nó **pools de mediação** e clique em **pool do servidor de mediação**.

4.  Em **definir novo pool de mediação**, digite o nome de domínio totalmente qualificado (FQDN) do pool do servidor de mediação.

5.  Em seguida, siga um destes procedimentos:
    
      - Se você deseja implantar vários servidores de mediação no pool para fornecer alta disponibilidade, selecione **pool de vários computadores**.
        
        <div>
        

        > [!NOTE]  
        > Você deve implantar o balanceamento de carga DNS para suportar pools do servidor de mediação que têm vários servidores de mediação. Para obter detalhes, consulte a seção usar o balanceamento de carga DNS em pools do servidor de mediação do <A href="lync-server-2013-dns-load-balancing.md">balanceamento de carga DNS no Lync Server 2013</A> na documentação de planejamento.

        
        </div>
    
      - Se você deseja implantar apenas um servidor de mediação no pool porque você não precisa de alta disponibilidade, selecione **pool de computador único**. Ignore a etapa seguinte.

6.  Se você selecionou **Pool de Vários Computadores** na etapa anterior, no item **Definir os computadores neste pool**, clique em **FQDN do Computador**, digite o FQDN de cada servidor no pool e clique em **Adicionar**. Repita essa etapa para todos os outros servidores de mediação que você deseja adicionar ao pool. Quando tiver definido todos os computadores no pool, clique em **Avançar**.

7.  Na página **selecionar o próximo salto** , clique em **pool de próximo salto**, clique no FQDN do pool de front-ends que usará este pool de servidor de mediação e clique em **Avançar**.

8.  Na página **Selecionar um Servidor de Borda**, execute um destes procedimentos:
    
      - Se quiser fornecer conectividade PSTN para usuários externos habilitados para o Enterprise Voice, em **selecionar pool de borda usado por este servidor de mediação**, clique no FQDN do pool do servidor de borda que usará este pool de servidor de mediação para fornecer conectividade PSTN aos usuários externos e clique em **Avançar**.
    
      - Se você não planeja habilitar usuários externos para o Enterprise Voice ou se não deseja fornecer conectividade PSTN aos usuários quando eles estão fora da rede interna, clique em **Avançar**.

9.  Em seguida, siga os procedimentos em [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação de implantação para adicionar o servidor de mediação à topologia. Você deve publicar sua topologia cada vez que usar o construtor de topologias para criar ou modificar sua topologia, de forma que os dados possam ser usados para instalar os arquivos para servidores que estão executando o Lync Server. Prossiga para as próximas etapas para modificar as portas de escuta do Servidor de Mediação, se necessário.

</div>

</div>

<div>

## <a name="define-the-mediation-server-listening-ports"></a>Definir as portas de escuta do servidor de mediação

Siga as etapas deste tópico para usar o construtor de topologias para definir as portas de escuta que um servidor de mediação ou pool aceitará conexões de entrada de um ponto de gateway.

<div>

## <a name="to-modify-the-mediation-server-listening-ports"></a>Para modificar as portas de escuta do servidor de mediação

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  No construtor de topologias, na árvore de console, expanda o nó **pools de mediação** e clique com o botão direito do mouse no servidor de mediação criado anteriormente.

3.  Por padrão, as portas de escuta SIP no servidor de mediação são 5070 para o tráfego TLS do Lync Server, 5067 para tráfego TLS de pares (gateways, PBXs ou SBCs). A porta TCP é desabilitada por padrão. Você deve habilitar a porta TCP se tiver gateways que não oferecem suporte a TLS.

4.  Especificar o intervalo de portas de escuta de TLS ou TCP desejado o servidor de mediação aceitará conexões de entrada de gateways PSTN.
    
    <div>
    

    > [!NOTE]  
    > Não é necessário inserir um intervalo de portas TCP se a opção <STRONG>Habilitar porta TCP</STRONG> não estiver marcada. Essa configuração é opcional.

    
    </div>

Em seguida, [defina um gateway no construtor de topologias no Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md) e instale os arquivos em cada servidor de mediação no pool seguindo os procedimentos em [instalar os arquivos para o servidor de mediação no Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md).

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

