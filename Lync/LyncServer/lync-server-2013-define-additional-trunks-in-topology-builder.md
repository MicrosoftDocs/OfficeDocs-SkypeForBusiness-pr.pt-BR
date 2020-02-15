---
title: 'Lync Server 2013: definir troncos adicionais no construtor de topologias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f88a292b11e617d1ae0d20f603ad53b2b2847e7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038133"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Definir troncos adicionais no construtor de topologias no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

Siga estas etapas para usar o construtor de topologias para definir um tronco adicional ao qual você pode associar um *ponto* a um servidor de mediação. Um ponto fornece aos usuários habilitados para o Enterprise Voice com conectividade com a rede telefônica pública comutada (PSTN). Um ponto pode ser um gateway PSTN, um IP-PBX ou um controlador de borda da sessão (SBC) para um provedor de serviços de telefonia da Internet (ITSP). O tronco define essa conexão entre o servidor de mediação e o ponto. Vários troncos podem ser definidos por servidor de mediação. Um servidor de mediação pode ser associado a vários pares.

Um tronco é uma conexão lógica entre um servidor de mediação e um gateway identificado exclusivamente pela tupla:

{Servidor de mediação FQDN, porta de escuta do servidor de mediação (TLS ou TCP): IP e FQDN do gateway, porta de escuta do gateway}

<div>


> [!NOTE]  
> Este tópico pressupõe que você tenha configurado um gateway PSTN e um tronco raiz com pelo menos um servidor ou pool de mediação autônomo ou localizado, conforme descrito em <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir um gateway no construtor de topologias no Lync Server 2013</A> na documentação de implantação.



</div>

<div>


> [!NOTE]  
> Este tópico pressupõe que você tenha configurado pelo menos um pool de front-ends ou servidor Standard Edition em pelo menos um site central, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and configure a front end pool or Standard Edition Server in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publish the Topology in Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir um tronco adicional entre um servidor de mediação e um ponto de gateway

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Em Lync Server 2013, o nome do site, **componentes compartilhados**, clique com o botão direito do mouse no nó **troncos** e, em seguida, clique em **novo tronco**.
    
    ![Tela da estrutura de arquivos do construtor de topologias do Lync Server](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Tela da estrutura de arquivos do construtor de topologias do Lync Server")

3.  Em **definir novo tronco**, especifique um nome amigável para identificar exclusivamente o tronco. Não é possível ter dois troncos com o mesmo nome.
    
    <div>
    

    > [!NOTE]  
    > Se você especificar Transport Layer Security (TLS) como o tipo de transporte, deverá especificar o FQDN em vez do endereço IP do par do servidor de mediação.

    
    </div>

4.  Em **Gateway PSTN associado**, selecione o ponto de gateway PSTN para associar a este tronco.
    
    ![Configurações de propriedade para o par de gateway PSTN para o tronco](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Configurações de propriedade para o par de gateway PSTN para o tronco")

5.  Em **porta de escuta para gateway PSTN**, digite a porta de escuta que o par (gateway PSTN, IP-PBX ou SBC) receberá mensagens SIP do servidor de mediação que serão associadas a esse tronco. As portas de par padrão são 5066 para TCP (Transmission Control Protocol) e 5067 para TLS (Transport Layer Security). As portas do aparelho de filial persistente padrão são 5081 para TCP e 5082 para TLS.

6.  Em **protocolo de transporte SIP**, clique no tipo de transporte que o ponto usa.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de segurança, é altamente recomendável implantar um ponto no servidor de mediação que possa usar o TLS.

    
    </div>

7.  Em **servidor de mediação associado**, selecione o pool do servidor de mediação a ser associado ao tronco raiz deste ponto

8.  Em **porta de servidor de mediação associada**, digite a porta de escuta que o servidor de mediação receberá mensagens SIP do ponto.
    
    <div>
    

    > [!NOTE]  
    > Com suporte a vários troncos no Lync Server 2013, dois troncos com nomes de tronco diferentes não podem ser configurados com a mesma <STRONG>porta de servidor de mediação associada</STRONG> e <STRONG>porta de escuta para gateway IP/PSTN</STRONG>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Com suporte a vários troncos no Lync Server 2013, várias portas de sinalização SIP podem ser definidas no servidor de mediação para comunicação com vários pares. Ao definir um tronco, o número da <STRONG>porta do servidor de mediação associado</STRONG> deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo servidor de mediação. Esse intervalo de porta é definido em pools do Lync Server 2013 e do servidor de mediação. Clique com o botão direito do mouse no pool do servidor de mediação relevante e selecione <STRONG>Editar propriedades</STRONG>. Especifique a faixa de porta no campo <STRONG>Portas de ouvinte</STRONG>.

    
    </div>

9.  Clique em **OK**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Modificar um tronco no construtor de topologia no Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

