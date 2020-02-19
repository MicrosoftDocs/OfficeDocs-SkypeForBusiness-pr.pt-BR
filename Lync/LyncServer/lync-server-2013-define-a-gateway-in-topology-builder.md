---
title: 'Lync Server 2013: definir um gateway no construtor de topologias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40881b38c83ebf254a60773060b642d183b7dfaa
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Definir um gateway no construtor de topologia no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-04_

Siga estas etapas para usar o construtor de topologias a fim de definir um *ponto* com o qual você pode associar um servidor de mediação para fornecer conectividade à rede telefônica pública comutada (PSTN) para usuários habilitados para o Enterprise Voice. Um ponto para o servidor de mediação pode ser um gateway PSTN, um IP-PBX ou um controlador de borda da sessão (SBC) para um provedor de serviços de telefonia da Internet (ITSP) ao qual você se conecta Configurando um tronco SIP.

<div>


> [!NOTE]  
> Este tópico pressupõe que você tenha configurado pelo menos um pool de front-ends interno ou servidor Standard Edition em pelo menos um site central com um servidor de mediação posicionado ou autônomo, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">define and configure a front end pool or Standard Edition Server in Lync server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publish the Topology in Lync Server 2013</A> na documentação de implantação. Este tópico também pressupõe que você verificou que sua infraestrutura atende aos pré-requisitos descritos nos <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">pré-requisitos de software para o Enterprise Voice no Lync server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">pré-requisitos de segurança e configuração para o Enterprise Voice no Lync Server 2013</A>.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>Definir um ponto para o Servidor de Mediação

1.  Inicie o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e em **Construtor de topologias do Lync Server**.

2.  Em Lync Server 2013, o nome do site, componentes compartilhados, clique com o botão direito do mouse no nó **gateways PSTN** e clique em **novo gateway PSTN**.
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1](images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  Em **Definir Novo Gateway IP/PSTN**, digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do ponto e clique em **Avançar**.
    
    ![8017ba5e-41bc-48d4-97d9-fd306cd322b8](images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48d4-97d9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > Se você especificar Transport Layer Security (TLS) como o tipo de transporte, deverá especificar o FQDN em vez do endereço IP do par do servidor de mediação.

    
    </div>

4.  Defina um modo de ouvinte (IPv4 ou IPv6) ou o endereço IP do seu novo gateway PSTN e clique em **Avançar**.
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec](images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  Defina um *tronco raiz* par ao gateway PSTN. Um tronco é uma conexão lógica entre um servidor de mediação e um gateway identificado exclusivamente pela tupla.
    
    {Servidor de mediação FQDN, porta de escuta do servidor de mediação (TLS ou TCP): IP e FQDN do gateway, porta de escuta do gateway}
    
      - Ao definir um gateway PSTN no construtor de topologia, você deve definir um tronco de raiz para adicionar com sucesso o gateway PSTN à sua topologia.
    
      - A árvore de raiz não pode ser removida até que o gateway PSTN associado seja removido.
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d](images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  Em **porta de escuta para gateway IP/PSTN**, digite a porta de escuta que o gateway, PBX ou SBC usará para mensagens SIP do servidor de mediação que serão associadas ao tronco raiz do gateway PSTN. (Por padrão, as portas são 5066 para protocolo TCP e 5067 para protocolo TLS em um gateway PSTN, PBX ou SBC. Em um aparelho de filial persistente em um site de filial, as portas padrão são 5081 para TCP e 5082 para TLS.

7.  Em **Protocolo de Transporte SIP**, clique no tipo de transporte que o ponto usa e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de segurança, é altamente recomendável implantar um ponto no servidor de mediação que possa usar o TLS.

    
    </div>

8.  Em **servidor de mediação associado**, selecione o pool do servidor de mediação a ser associado ao tronco raiz desse gateway PSTN.

9.  Em **porta de servidor de mediação associada**, digite a porta de escuta que o servidor de mediação usará para mensagens SIP do gateway.
    
    <div>
    

    > [!NOTE]  
    > Com suporte a vários troncos no Lync Server 2013, várias portas de sinalização SIP podem ser definidas no servidor de mediação a ser usado para comunicação com vários gateways PSTN. Ao definir um tronco, a <STRONG>porta do servidor de mediação associada</STRONG> deve estar dentro do intervalo das portas de escuta para o respectivo protocolo permitido pelo servidor de mediação. Esse intervalo de porta é definido em pools do Lync Server 2013 e Mediation. Clique com o botão direito do mouse no pool de servidores de mediação de interesse e selecione <STRONG>Editar propriedades</STRONG>. Especifique a faixa de porta no campo <STRONG>Portas de ouvinte</STRONG>.

    
    </div>

10. Clique em **Concluir**.

<div>


> [!IMPORTANT]  
> Antes de finalizar esta etapa, certifique-se se o ponto definido está funcionando e usando o FQDN ou o endereço IP que você especificou.



</div>

Em seguida, para adicionar o par à topologia, siga os procedimentos em [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação de implantação. Você deve publicar sua topologia cada vez que usar o construtor de topologias para criar ou modificar sua topologia, para que os dados possam ser usados para instalar os arquivos para servidores que estão executando o Lync Server.

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

