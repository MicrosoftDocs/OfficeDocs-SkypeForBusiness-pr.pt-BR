---
title: 'Lync Server 2013: configurar DNS para suporte de borda'
description: 'Lync Server 2013: configurar DNS para suporte de borda.'
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
ms.openlocfilehash: 706f4915adda58dbb72b8dd8921e0cc612833718
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555887"
---
# <a name="configure-dns-for-edge-support-in-lync-server-2013"></a>Configurar o DNS para suporte de borda no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-15_

Você deve configurar os registros de DNS (Sistema de Nomes de Domínio) para interfaces de borda internas e externas, incluindo ambas as interfaces do Servidor de Borda e do proxy reverso. Como padrão, os Servidores de Borda não são reunidos em um domínio e não têm um nome de domínio totalmente qualificado. O Servidor de Borda é referenciado apenas pelo nome (de máquina) curto, não um nome de domínio totalmente qualificado. No entanto, o construtor de topologias usa FQDNs, não nomes curtos. O nome do servidor de borda deve corresponder ao FQDN usado pelo construtor de topologias. Para isso, você define um sufixo DNS que, ao ser combinado como nome de máquina, resulta no FQDN esperado. Use o seguinte procedimento em "Para adicionar o sufixo DNS do nome do computador em um Servidor de Borda que não está associado a um domínio" para adicionar o sufixo DNS ao nome do computador.

<div>


> [!NOTE]  
> Por padrão, o DNS usa um algoritmo Round Robin para girar a ordem dos dados de registro de recurso retornados nas respostas da consulta, onde há vários registros de recursos do mesmo tipo para um nome de domínio DNS consultado. O balanceamento de carga DNS do Lync Server 2013 depende do rodízio de DNS como parte do mecanismo de balanceamento de carga de DNS. Verifique se a configuração Round-Robin não foi desativada. Se você estiver usando um servidor DNS que não esteja executando um sistema operacional Windows, verifique se a classificação de registro de recurso Round-Robin está habilitada.



</div>

Use os procedimentos a seguir em “**Para criar um registro DNS SRV**” para criar e verificar cada registro DNS SRV. Use o procedimento em “**Para criar um registro A de DNS**” para definir os registros A de DNS necessários para acesso do usuário externo. Para confirmar que os registros estão configurados e funcionando corretamente, consulte “**Para verificar um registro DNS**” neste tópico. Para obter detalhes sobre cada registro necessário para dar suporte ao acesso de usuário externo, consulte [determine DNS Requirements for Lync Server 2013](lync-server-2013-determine-dns-requirements.md).

<div>

## <a name="to-add-the-dns-suffix-to-the-computer-name-on-an-edge-server-that-is-not-joined-to-a-domain"></a>Para adicionar o sufixo DNS do nome do computador em um Servidor de Borda que não está associado a um domínio

1.  No computador, clique em **Iniciar**, clique com o botão direito do mouse em **cComputador** e clique em **Propriedades**.

2.  Em **Nome do computador, domínio e configurações de grupo de trabalho**, clique em **Alterar configurações**.

3.  Na guia **Nome do Computador**, clique em **Alterar**.

4.  Em   **Alterações de Nome/Domínio do Computador**, clique em **Mais**.

5.  Em **Sufixo DNS e nome NetBIOS do computador**, no **Sufixo DNS primário deste computador**, digite o nome de seu domínio interno (por exemplo, corp.contoso.com) e clique em **OK** três vezes.

6.  Reinicie o computador.

</div>

<div>

## <a name="to-create-a-dns-srv-record"></a>Para criar um registro SRV de DNS

1.  No servidor DNS apropriado, clique em **Iniciar**, clique em **Painel de Controle**, clique em **Ferramentas Administrativas** e, em seguida, clique em **DNS**.
    
    <div>
    

    > [!IMPORTANT]  
    > Você precisa configurar o DNS para que haja: 1) entradas DNS externas para pesquisas de DNS externas por usuários remotos e parceiros federados; 2) entradas de pesquisa de DNS para uso pelos servidores de borda dentro da rede de perímetro (também conhecida como DMZ, zona desmilitarizada e sub-rede filtrada), incluindo registros para os servidores internos que executam o Lync Server 2013; e 3) entradas de DNS internas para pesquisas pelos clientes internos e servidores que executam o Lync Server 2013.

    
    </div>

2.  Na árvore do console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio onde o Lync Server 2013 está instalado.

3.  Clique em **Outros Registros Novos**.

4.  Em **Selecione um tipo de registro de recurso**, digite o **Local do Serviço (SRV)** e, em seguida, clique em **Criar Registro**.

5.  Forneça todas as informações exigidas para o registro SRV de DNS.

</div>

<div>

## <a name="to-create-a-dns-a-record"></a>Para criar um registro A de DNS

1.  No servidor DNS, clique em **Iniciar**, clique em **Painel de Controle**, clique em **Ferramentas Administrativas** e, em seguida, clique em **DNS**.

2.  Na árvore do console do seu domínio SIP, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 está instalado.

3.  Clique em **Novo Host (A)**.

4.  Forneça todas as informações exigidas para o registro SRV de DNS.

</div>

<div>

## <a name="to-verify-a-dns-record"></a>Para verificar um registro DNS

1.  Faça logon em um computador cliente no domínio.

2.  Clique em **Iniciar** e em **Executar**.

3.  No prompt de comando, execute o seguinte comando:
    
        nslookup <FQDN edge interface>

4.  Verifique se você recebe uma resposta que resolve o endereço IP apropriado para o FQDN.

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar um registro SRV de DNS para integração com a UM do Exchange hospedado](lync-server-2013-create-a-dns-srv-record-for-integration-with-hosted-exchange-um.md)  


[Determinar requisitos de DNS para o Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

