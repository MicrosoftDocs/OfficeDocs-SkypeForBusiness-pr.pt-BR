---
title: 'Lync Server 2013: Configurar DNS para suporte à borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS for edge support
ms:assetid: 955493e6-aa29-424d-bb81-1ef87b3b15e3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398756(v=OCS.15)
ms:contentKeyID: 48184894
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c905c8fff7a67b26a7df8d2c741ce0a16fddce6c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Configurar DNS para suporte à borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-15_

Você deve configurar registros DNS (sistema de nomes de domínio) para interfaces de borda internas e externas, incluindo ambas as interfaces do servidor de borda e proxy reverso. Por padrão, os servidores de borda não fazem parte de um domínio e não terão um nome de domínio totalmente qualificado (nome de domínio totalmente qualificado). O servidor de borda é chamado apenas pelo nome curto (máquina), não por um nome de domínio totalmente qualificado. No entanto, o construtor de topologias usa FQDNs, não nomes curtos. O nome do servidor de borda deve corresponder ao FQDN usado pelo construtor de topologias. Para fazer isso, você define um sufixo DNS que, quando combinado com o nome do computador, resulta no FQDN esperado. Use o procedimento a seguir em "para adicionar o sufixo DNS ao nome do computador e no servidor de borda que não está associado a um domínio" para adicionar o sufixo DNS ao nome do computador.

<div>


> [!NOTE]  
> Por padrão, o DNS usa um algoritmo de rodízio para girar a ordem dos dados de registro de recurso retornados nas respostas de consulta onde vários registros de recursos do mesmo tipo existem para um nome de domínio DNS consultado. O balanceamento de carga de DNS do Lync Server 2013 depende do rodízio do DNS como parte do mecanismo de balanceamento de carga de DNS. Verifique se a configuração de rodízio não foi desabilitada. Se você estiver usando um servidor DNS que não está executando um sistema operacional Windows, verifique se a ordem de registro de recursos de rodízio está habilitada.



</div>

Use os procedimentos a seguir em "**para criar um registro SRV DNS**" para criar e verificar cada registro SRV DNS. Use o procedimento em "**criar um registro DNS**a" para definir os registros DNS a necessários para o acesso de usuários externos. Para confirmar se os registros estão configurados e funcionando corretamente, consulte "**para verificar um registro DNS**" neste tópico. Para obter detalhes sobre cada registro necessário para dar suporte a acesso externo a usuários, consulte [determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>Para adicionar o sufixo DNS ao nome do computador em um servidor de borda que não está associado a um domínio

1.  No computador, clique em **Iniciar**, clique com o botão direito do mouse em **computador**e, em seguida, clique em **Propriedades**.

2.  Em **nome do computador, domínio e configurações de grupo de trabalho**, clique em **alterar configurações**.

3.  Na guia **nome do computador** , clique em **alterar**.

4.  Em **nome do computador/alterações de domínio**, clique em **mais**.

5.  Em **sufixo DNS e nome NetBIOS do computador**, no **sufixo DNS primário deste computador**, digite o nome do seu domínio interno (por exemplo, Corp.contoso.com) e clique em **OK** três vezes.

6.  Reinicie o computador.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>Para criar um registro SRV DNS

1.  No servidor DNS apropriado, clique em **Iniciar**, clique em **painel de controle**, clique em **Ferramentas administrativas**e clique em **DNS**.
    
    <div>
    

    > [!IMPORTANT]  
    > Você precisa configurar o DNS para que haja: 1) entradas DNS externas para pesquisas de DNS externas por usuários remotos e parceiros federados; 2) entradas para pesquisas de DNS para uso pelos servidores de borda dentro da rede de perímetro (também conhecido como DMZ, zona desmilitarizada e sub-rede filtrada), incluindo registros para os servidores internos que executam o Lync Server 2013; e 3) entradas DNS internas para pesquisas pelos clientes internos e servidores que executam o Lync Server 2013.

    
    </div>

2.  Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio onde o Lync Server 2013 está instalado.

3.  Clique em **outros novos registros**.

4.  Em **Selecione um tipo de registro de recurso**, digite **local do serviço (SRV)** e clique em **criar registro**.

5.  Forneça todas as informações necessárias para o registro SRV DNS.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>Para criar um registro de DNS A

1.  No servidor DNS, clique em **Iniciar**, clique em **painel de controle**, clique em **Ferramentas administrativas**e, em seguida, clique em **DNS**.

2.  Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 está instalado.

3.  Clique em **novo host (A)**.

4.  Forneça todas as informações necessárias para o registro SRV DNS.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>Para verificar um registro DNS

1.  Faça logon em um computador cliente no domínio.

2.  Clique em  **Iniciar ** e em  **Executar **.

3.  No prompt de comando, execute o seguinte comando:
    
        nslookup <FQDN edge interface>

4.  Verifique se você recebe uma resposta que é resolvida para o endereço IP apropriado para o FQDN.

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar um registro DNS SRV para integração com Exchange UM hospedado](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Determinar requisitios de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

