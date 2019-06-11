---
title: 'Lync Server 2013: definir um gateway no construtor de topologias'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Define a gateway in Topology Builder
ms:assetid: 456e5a96-d9f6-42a6-862c-a69464391628
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425945(v=OCS.15)
ms:contentKeyID: 48184036
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c9e57ad4e3d8c1692731bcfd4a56dc5c3d05bda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829727"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-a-gateway-in-topology-builder-in-lync-server-2013"></a>Definir um gateway no construtor de topologias no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-04_

Siga estas etapas para usar o construtor de topologias para definir um *par* com o qual você pode associar um servidor de mediação para fornecer conectividade à rede telefônica pública comutada (PSTN) para usuários habilitados para Enterprise Voice. Um peer para o servidor de mediação pode ser um gateway PSTN, um IP-PBX ou um controlador de borda de sessão (SBC) para um provedor de serviços de telefonia pela Internet (ITSP) ao qual você se conecta Configurando um tronco SIP.

<div>


> [!NOTE]  
> Este tópico pressupõe que você tenha configurado pelo menos um servidor front-end interno ou um servidor Standard Edition em pelo menos um site central com um servidor de mediação posicionado ou autônomo, conforme descrito em <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">definir e configurar um pool de front-end ou um servidor Standard Edition em Lync Server 2013</A> e <A href="lync-server-2013-publish-the-topology.md">publicar a topologia no Lync Server 2013</A> na documentação de implantação. Este tópico também pressupõe que você verificou que sua infraestrutura atende aos pré-requisitos descritos em <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">pré-requisitos de software para o Enterprise Voice no Lync Server 2013</A> e <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">pré-requisitos de segurança e configuração do Enterprise Voice no Lync Server 2013</A>.



</div>

<div>

## <a name="to-define-a-peer-for-the-mediation-server"></a>Para definir um par para o servidor de mediação

1.  Iniciar o construtor de topologias: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Construtor de topologias do Lync Server**.

2.  Em Lync Server 2013, o nome do seu site, componentes compartilhados, clique com o botão direito do mouse no nó **gateways PSTN** e, em seguida, clique em **novo gateway PSTN**.
    
    ![d898c3c1-8798-4b74-8f02-b994ef3db4c1] (images/Gg425945.d898c3c1-8798-4b74-8f02-b994ef3db4c1(OCS.15).png "d898c3c1-8798-4b74-8f02-b994ef3db4c1")

3.  Em **Definir Novo Gateway IP/PSTN**, digite o nome de domínio totalmente qualificado (FQDN) ou o endereço IP do ponto e clique em **Avançar**.
    
    ![8017ba5e-41bc-48D4-97D9-fd306cd322b8] (images/Gg425945.8017ba5e-41bc-48d4-97d9-fd306cd322b8(OCS.15).png "8017ba5e-41bc-48D4-97D9-fd306cd322b8")
    
    <div>
    

    > [!NOTE]  
    > Se você especificar Transport Layer Security (TLS) como o tipo de transporte, você deve especificar o FQDN em vez do endereço IP do par do servidor de mediação.

    
    </div>

4.  Defina um modo de ouvinte (IPv4 ou IPv6) ou o endereço IP do seu novo gateway PSTN e clique em **Avançar**.
    
    ![c7fc0d12-adc8-45a7-aca1-b376e1d2fcec] (images/Gg425945.c7fc0d12-adc8-45a7-aca1-b376e1d2fcec(OCS.15).png "c7fc0d12-adc8-45a7-aca1-b376e1d2fcec")

5.  Defina um *tronco raiz* para o gateway PSTN. Um tronco é uma conexão lógica entre um servidor de mediação e um gateway identificado exclusivamente pela tupla.
    
    {Servidor de mediação do FQDN, porta de escuta do servidor de mediação (TLS ou TCP): IP e FQDN do gateway, porta de escuta do gateway}
    
      - Ao definir um gateway PSTN no construtor de topologias, você deve definir um tronco raiz para adicionar com êxito o gateway PSTN à sua topologia.
    
      - A árvore de raiz não pode ser removida até que o gateway PSTN associado seja removido.
    
    ![3b030757-eb35-4616-bb6b-74ee67507e3d] (images/Gg425945.3b030757-eb35-4616-bb6b-74ee67507e3d(OCS.15).png "3b030757-eb35-4616-bb6b-74ee67507e3d")

6.  Em **porta de escuta para gateway IP/PSTN**, digite a porta de escuta que o gateway, PBX ou SBC usará para mensagens SIP do servidor de mediação que serão associadas ao tronco raiz do gateway PSTN. (Por padrão, as portas são 5066 para protocolo TCP e 5067 para protocolo TLS em um gateway PSTN, PBX ou SBC. Em um aparelho de ramificação sobreviventes em um site de filial, as portas padrão são 5081 para TCP e 5082 para TLS.)

7.  Em **Protocolo de Transporte SIP**, clique no tipo de transporte que o ponto usa e clique em **OK**.
    
    <div>
    

    > [!NOTE]  
    > Por motivos de segurança, recomendamos enfaticamente que você implante um par para o servidor de mediação que possa usar TLS.

    
    </div>

8.  Em **servidor de mediação associado**, selecione o pool do servidor de mediação para associar ao tronco raiz desse gateway PSTN.

9.  Em **porta do servidor de mediação associada**, digite a porta de escuta que o servidor de mediação usará para mensagens SIP do gateway.
    
    <div>
    

    > [!NOTE]  
    > Com o suporte a vários troncos no Lync Server 2013, várias portas de sinalização SIP podem ser definidas no servidor de mediação para serem usadas para comunicação com vários gateways PSTN. Ao definir um tronco, a <STRONG>porta do servidor de mediação associada</STRONG> deve estar dentro do intervalo das portas de escuta do respectivo protocolo permitido pelo servidor de mediação. Esse intervalo de porta é definido em pools do Lync Server 2013 e Mediation. Clique com o botão direito do mouse no pool de servidores de mediação de interesse e selecione <STRONG>Editar propriedades</STRONG>. Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

10. Clique em **Concluir**.

<div>


> [!IMPORTANT]  
> Antes de concluir esta etapa, verifique se o par que você definiu está em execução e usando o FQDN ou endereço IP que você especificou.



</div>

Em seguida, para adicionar o par à topologia, siga os procedimentos em [publicar a topologia no Lync Server 2013](lync-server-2013-publish-the-topology.md) na documentação de implantação. Você deve publicar sua topologia toda vez que usar o construtor de topologias para criar ou modificar sua topologia, para que os dados possam ser usados para instalar os arquivos para servidores que estão executando o Lync Server.

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

