---
title: Criar um registro SRV de DNS para integração com a UM do Exchange hospedado
description: Criar um registro SRV de DNS para integração com a UM do Exchange hospedado.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694a595977abe33bebbb5fbcf2a508c9bb4e35a4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542137"
---
# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Criar um registro SRV de DNS para integração com a UM do Exchange hospedado

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-20_

Este tópico descreve como configurar o registro SRV do sistema de nomes de domínio (DNS) que é necessário para um servidor de borda do Lync Server 2013 para rotear para um serviço do Exchange hospedado, como o Microsoft Exchange Online.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>Para criar um registro SRV de DNS para o serviço Exchange hospedado

1.  Faça logon no servidor DNS externo como membro do grupo DnsAdmins.

2.  Clique em **Iniciar**,  **Ferramentas Administrativas** e em **DNS**.

3.  Na árvore do console do seu domínio SIP, expanda **zonas de pesquisa direta**e selecione o domínio SIP no qual o Lync Server 2013 será instalado.
    
    <div>
    

    > [!IMPORTANT]
    > Você deve criar o registro SRV do DNS no domínio SIP em que o Lync Server está ou será instalado. Ao criar o registro SRV, o FQDN usado para o Host que está oferecendo este campo de serviço deve ser o FQDN externo do pool de Borda. Por exemplo, se o FQDN do seu pool de Borda for edge01.contoso.net, insira este valor. Este também deve ser o mesmo domínio do registro Hosts do DNS (A).

    
    </div>

4.  Clique com o botão direito no domínio selecionado e clique em **Outros Registros Novos**.

5.  Em **Tipo de Registro de Recurso**, clique em **Local do serviço (SRV)** e em **Criar registro**.

6.  Em **novo registro de recurso**, clique em **serviço**e digite ** \_ sipfederationtls**.

7.  Clique em **protocolo**e digite ** \_ TCP**.

8.  Clique em **Número da Porta** e digite **5061**.

9.  Clique em host que oferece **este serviço**e digite o nome de domínio totalmente qualificado (FQDN) do pool de borda do lync Server 2013 que fornece acesso ao seu sistema do lync Server 2013 para clientes externos confiáveis.
    
    <div>
    

    > [!NOTE]
    > O domínio também deve ser configurado como um domínio autoritativo, aceito em suas configurações do Exchange Online. Para obter detalhes, consulte criar domínios aceitos em <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A> .

    
    </div>

10. Clique em **OK** e em **Concluído**.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>Para verificar se o registro SRV de DNS foi criado com êxito

1.  Faça logon em um computador cliente no domínio.

2.  Clique em **Iniciar** e em **Executar**.

3.  No prompt de comando, execute o seguinte comando:
    
        nslookup <FQDN Lync Edge Pool>

4.  Verifique se você recebe uma resposta que resolve o endereço IP apropriado para o FQDN.

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar registros DNS para servidores de proxy reverso no Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

