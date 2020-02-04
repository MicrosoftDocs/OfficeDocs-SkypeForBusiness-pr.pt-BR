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
ms.openlocfilehash: c55e8073bd1ad1bb2db69096e4e58aa2b148e775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>Definir troncos adicionais no construtor de topologias no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

Siga estas etapas para usar o construtor de topologias para definir um tronco adicional ao qual você pode associar um *par* com um servidor de mediação. Um par fornece aos usuários habilitados para o Enterprise Voice com conectividade com a rede telefônica pública comutada (PSTN). Um ponto pode ser um gateway PSTN, um PBX IP ou um Controlador de Borda da Sessão (SBC) para um Provedor de Serviço Telefônico de Internet (ITSP). O tronco define essa conexão entre o servidor de mediação e o par. Vários troncos podem ser definidos por servidor de mediação. Um servidor de mediação pode ser associado a vários pares.

Um tronco é uma conexão lógica entre um servidor de mediação e um gateway identificado exclusivamente pela tupla:

{Servidor de mediação do FQDN, porta de escuta do servidor de mediação (TLS ou TCP): IP e FQDN do gateway, porta de escuta do gateway}

<div>


> [!NOTE]  
> Este tópico pressupõe que você tenha configurado um gateway PSTN e um tronco raiz com pelo menos um servidor ou pool de mediação posicionado ou autônomo, conforme descrito em <A href="lync-server-2013-define-a-gateway-in-topology-builder.md">definir um gateway no construtor de topologias no Lync Server 2013</A> na documentação de implantação.



</div>

<div>


> [!NOTE]  
> Este tópico pressupõe que você tenha configurado pelo menos um servidor front-end ou um servidor Standard Edition em pelo menos um site central, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir e configurar um servidor front-end ou um servidor Standard Edition no Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publicar a topologia no Lync Server 2013</A> na documentação de implantação.



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>Para definir um tronco adicional entre um servidor de mediação e um gateway de mesmo nível

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Em Lync Server 2013, o nome do seu site, **componentes compartilhados**, clique com o botão direito do mouse no nó **troncos** e, em seguida, clique em **novo tronco**.
    
    ![Tela de estrutura de arquivos do Lync Server Topology Builder](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Tela de estrutura de arquivos do Lync Server Topology Builder")

3.  Em **Definir Novo Tronco**, especifique um nome amigável para identificar exclusivamente o tronco. Você não pode ter dois troncos com o mesmo nome.
    
    <div>
    

    > [!NOTE]  
    > Se você especificar Transport Layer Security (TLS) como o tipo de transporte, você deve especificar o FQDN em vez do endereço IP do par do servidor de mediação.

    
    </div>

4.  Sob **Gateway PSTN associado**, selecione o ponto de gateway PSTN para associar a este tronco.
    
    ![Configurações de Propriedade do par de gateway PSTN para o tronco](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "Configurações de Propriedade do par de gateway PSTN para o tronco")

5.  Em **porta de escuta para gateway PSTN**, digite a porta de escuta que o par (gateway PSTN, PBX de IP ou SBC) receberá mensagens SIP do servidor de mediação que serão associadas a esse tronco. As portas de ponto padrão são 5066 para TCP (Transmission Control Protocol) e 5067 para TLS (Transport Layer Security). As portas da ramificação sobreviventes padrão são 5081 para TCP e 5082 para TLS.

6.  Sob **Protocolo de Transporte SIP**, clique no tipo de transporte usado pelo ponto.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de segurança, recomendamos enfaticamente que você implante um par para o servidor de mediação que possa usar TLS.

    
    </div>

7.  Em **servidor de mediação associado**, selecione o pool do servidor de mediação para associar ao tronco raiz desse par

8.  Em **porta do servidor de mediação associada**, digite a porta de escuta que o servidor de mediação receberá mensagens SIP do par.
    
    <div>
    

    > [!NOTE]  
    > Com o suporte a vários troncos no Lync Server 2013, dois troncos com diferentes nomes de tronco não podem ser configurados com a mesma <STRONG>porta do servidor de mediação associada</STRONG> e <STRONG>porta de escuta do gateway IP/PSTN</STRONG>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Com o suporte a vários troncos no Lync Server 2013, várias portas de sinalização SIP podem ser definidas no servidor de mediação para comunicação com vários pares. Ao definir um tronco, o número da <STRONG>porta do servidor de mediação associado</STRONG> deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo servidor de mediação. Esse intervalo de porta é definido nos pools do Lync Server 2013 e do servidor de mediação. Clique com o botão direito do mouse no pool do servidor de mediação relevante e selecione <STRONG>Editar propriedades</STRONG>. Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

9.  Clique em **OK**.

</div>

<div>

## <a name="see-also"></a>Confira também


[Modificar um tronco no construtor de topologias no Lync Server 2013](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

