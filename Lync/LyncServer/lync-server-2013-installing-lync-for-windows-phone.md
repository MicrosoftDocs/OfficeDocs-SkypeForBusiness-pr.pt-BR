---
title: 'Lync Server 2013: Instalando o Lync para Windows Phone'
description: 'Lync Server 2013: Instalando o Lync para Windows Phone.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f5da90a5dc0babdc6944e4f9c426fe896d4f156
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573977"
---
# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Instalando o Lync para Windows Phone no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-02-03_

O Lync 2013 para Windows Phone é um aplicativo instalável pelo usuário que está disponível no Windows Phone Marketplace.

<div>

## <a name="installing-lync-for-windows-mobile"></a>Instalando o Lync para Windows Mobile

Você pode instruir seus usuários a instalar o Lync 2013 para Windows Phone em seus dispositivos direcionando-os para o Windows Phone Marketplace em <https://go.microsoft.com/fwlink/p/?linkid=231901> .

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>Se você usar um registro SRV de DNS para publicar serviços Web do Exchange

Para habilitar a integração do Exchange para clientes do Lync, algumas organizações publicam a URL dos serviços Web do Exchange usando um registro SRV de DNS. O documento "entendendo e Solucionando problemas de integração do Exchange", disponível no centro de download da Microsoft em [https://go.microsoft.com/fwlink/?LinkID=391095](https://go.microsoft.com/fwlink/?linkid=391095) , descreve cenários nos quais isso pode ser necessário. No entanto, a integração do Exchange para usuários do Windows Phone não funcionará nesse cenário, porque a plataforma Windows Phone não oferece suporte a pesquisas SRV. Você precisará instruir os usuários do Windows Phone a especificar a URL dos serviços Web do Exchange, em vez de permitir que o telefone detecte automaticamente o servidor.

Instrua os usuários a definir as configurações do Lync em seus telefones Windows da seguinte maneira:

1.  No Windows Phone, nas configurações do Lync, selecione a tela do **Exchange** .

2.  Mova o **servidor de detecção automática** para **desativado**.

3.  Toque no campo vazio e digite o nome de domínio totalmente qualificado (FQDN) ou a URL dos serviços Web do Exchange.
    
    <div>
    

    > [!NOTE]  
    > Você pode especificar o FQDN (nome de domínio totalmente qualificado) ou a URL completa do seu servidor de serviços Web do Exchange. Se você especificar o FQDN, o protocolo (https://) e o caminho do serviços Web do Exchange (/EWS/Exchange.asmx) serão adicionados automaticamente. Se o caminho dos serviços Web do Exchange for diferente, você poderá especificar a URL completa.

    
    </div>

4.  Feche a tela.

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>Verificando a instalação do cliente móvel

Depois de configurar o cliente e entrar com êxito, use os seguintes testes para verificar se a instalação do Lync 2013 está funcionando corretamente no seu dispositivo móvel.

**Procure um contato no diretório corporativo**

1.  Na lista Contatos, toque em **Pesquisar** na parte inferior.

2.  Procure um contato que conste apenas na lista de endereços global.

3.  Verifique se o nome do contato aparece nos resultados da pesquisa.

**Testar mensagens instantâneas e presença**

1.  Na lista Contatos, toque em um contato.

2.  No cartão de visita, toque no ícone **IM**.

3.  Verifique se uma janela de mensagens instantâneas (IM) aparece e se é possível digitar e enviar uma mensagem instantânea.

**Teste a conferência discada**

1.  No Outlook, agende uma reunião do Lync.

2.  No dispositivo móvel, abra o convite de reunião.

3.  Clique no link da reunião para ingressar.

4.  Atenda à chamada do serviço de conferência e verifique se você está conectado ao áudio da reunião.

**Teste as notificações por push**

1.  No dispositivo móvel do usuário A, entre no Lync com a conta do usuário A.

2.  Abra outro aplicativo no dispositivo móvel.

3.  Em um cliente diferente, entre no Lync com a conta do usuário B.

4.  Envie uma mensagem instantânea do usuário B para o usuário A.

5.  Verifique se a notificação de IM aparece no dispositivo móvel do usuário A.

</div>

</div>

<span> </span>

</div>

</div>

</div>

