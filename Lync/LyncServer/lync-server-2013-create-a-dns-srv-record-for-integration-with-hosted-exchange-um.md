---
title: Criar um registro DNS SRV para integração com Exchange UM hospedado
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
ms.openlocfilehash: c8cc5072e122d553007a2b4e095c58988aca390d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740451"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Criar um registro DNS SRV para integração com Exchange UM hospedado

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-20_

Este tópico descreve como configurar o registro SRV do sistema de nome de domínio (DNS) necessário para um servidor de borda do Lync Server 2013 para direcionar para um serviço do Exchange hospedado, como o Microsoft Exchange Online.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>Para criar um registro SRV DNS externo para o serviço hospedado do Exchange

1.  Faça logon no servidor DNS externo como membro do grupo DnsAdmins.

2.  Clique em **Iniciar**, clique em **Ferramentas administrativas**e, em seguida, clique em **DNS**.

3.  Na árvore de console do seu domínio SIP, expanda **zonas de pesquisa direta**e selecione o domínio SIP no qual o Lync Server 2013 será instalado.
    
    <div>
    

    > [!IMPORTANT]
    > Você deve criar o registro SRV DNS no domínio SIP no qual o Lync Server está ou será instalado. Quando você cria o registro SRV, o FQDN usado para o host que oferece este campo de serviço deve ser o FQDN externo do pool de borda. Por exemplo, se o FQDN externo do seu pool de bordas for edge01.contoso.net, insira esse valor. Isso também deve estar no mesmo domínio que o registro de hosts DNS (A).

    
    </div>

4.  Clique com o botão direito do mouse no domínio selecionado e, em seguida, clique em **outros novos registros**.

5.  Em **tipo de registro de recurso**, clique em **local do serviço (SRV)** e, em seguida, clique em **criar registro**.

6.  Em **novo registro de recurso**, clique em **serviço**e, em seguida, digite ** \_sipfederationtls**.

7.  Clique em **protocolo**e digite ** \_TCP**.

8.  Clique em **Número da porta** e digite **5061**.

9.  Clique em **host que oferece esse serviço**e digite o nome de domínio totalmente qualificado (FQDN) do pool de bordas do lync Server 2013 que fornece acesso ao seu sistema do lync Server 2013 para clientes externos confiáveis.
    
    <div>
    

    > [!NOTE]
    > O domínio também deve ser configurado como um domínio autoritativo aceito nas configurações do Exchange Online. Para obter detalhes, consulte criar domínios aceitos em <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.

    
    </div>

10. Clique em **OK** e em **Concluído**.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>Para verificar se o registro SRV DNS foi criado com êxito

1.  Faça logon em um computador cliente no domínio.

2.  Clique em  **Iniciar ** e em  **Executar **.

3.  No prompt de comando, execute o seguinte comando:
    
        nslookup <FQDN Lync Edge Pool>

4.  Verifique se você recebe uma resposta que é resolvida para o endereço IP apropriado para o FQDN.

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar registros de DNS para servidores de proxy reverso no Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

