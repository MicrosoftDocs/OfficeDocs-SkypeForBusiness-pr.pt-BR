---
title: 'Lync Server 2013: Instalando o Lync para Windows Phone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Installing Lync for Windows Phone
ms:assetid: bf502546-ff69-489f-a92e-a78b58803d53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690996(v=OCS.15)
ms:contentKeyID: 51541513
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aeb8f43ea4f4db15a9a057bd0d7b24c55d858cb3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-lync-for-windows-phone-in-lync-server-2013"></a>Instalar o Lync para Windows Phone no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-02-03_

O Lync 2013 para Windows Phone é um aplicativo instalável pelo usuário que está disponível no Windows Phone Marketplace.

<div>

## <a name="installing-lync-for-windows-mobile"></a>Instalando o Lync para Windows Mobile

Você pode instruir os usuários a instalar o Lync 2013 para Windows Phone em seus dispositivos direcionando-os para o Windows Phone <http://go.microsoft.com/fwlink/p/?linkid=231901>Marketplace em.

</div>

<div>

## <a name="if-you-use-a-dns-srv-record-to-publish-exchange-web-services"></a>Se você usar um registro SRV DNS para publicar serviços Web do Exchange

Para habilitar a integração do Exchange para clientes do Lync, algumas organizações publicam a URL dos serviços Web do Exchange usando um registro de servidor DNS. O documento "entendendo e Solucionando problemas de integração do Exchange", disponível no centro [http://go.microsoft.com/fwlink/?LinkID=391095](http://go.microsoft.com/fwlink/?linkid=391095)de download da Microsoft em, descreve cenários em que isso pode ser necessário. No entanto, a integração do Exchange para usuários do Windows Phone não funcionará nesse cenário, porque a plataforma do Windows Phone não oferece suporte a pesquisas SRV. Você precisará instruir os usuários do Windows Phone a especificar a URL dos serviços Web do Exchange em vez de permitir que o telefone detecte automaticamente o servidor.

Instrua os usuários a definir as configurações do Lync nos telefones Windows da seguinte maneira:

1.  No Windows Phone, nas configurações do Lync, selecione a tela do **Exchange** .

2.  Mova o **servidor de detecção automática** para **desativado**.

3.  Toque no campo vazio e insira o nome de domínio totalmente qualificado (FQDN) ou a URL dos serviços Web do Exchange.
    
    <div>
    

    > [!NOTE]  
    > Você pode especificar o nome de domínio totalmente qualificado (FQDN) ou a URL completa do servidor de serviços Web do Exchange. Se você especificar o FQDN, o protocolo (https://) e o caminho dos serviços Web do Exchange (/EWS/Exchange.asmx) serão adicionados automaticamente. Se o caminho dos serviços Web do Exchange for diferente, você poderá especificar a URL completa.

    
    </div>

4.  Fechar a tela.

</div>

<div>

## <a name="verifying-mobile-client-installation"></a>Verificando a instalação do cliente móvel

Depois de configurar o cliente e entrar com êxito, use os seguintes testes para verificar se a sua instalação do Lync 2013 está funcionando corretamente em seu dispositivo móvel.

**Procure um contato no diretório corporativo**

1.  Na lista de contatos, toque em **Pesquisar** na parte inferior.

2.  Procure um contato que conste apenas na lista de endereços global.

3.  Verifique se o nome do contato aparece nos resultados da pesquisa.

**Teste mensagens instantâneas e presença**

1.  Na lista Contatos, toque em um contato.

2.  No cartão de visita, toque no ícone de **mensagem instantânea** .

3.  Verifique se uma janela de mensagem instantânea (IM) aparece e se é possível digitar e enviar uma IM.

**Teste a conferência discada**

1.  No Outlook, agendar uma reunião do Lync.

2.  No dispositivo móvel, abra o convite de reunião.

3.  Clique no link da reunião para ingressar.

4.  Atenda à chamada do serviço de conferência e verifique se você está conectado ao áudio da reunião.

**Teste as notificações por push**

1.  No dispositivo móvel do usuário A, entre no Lync com A conta do usuário A.

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

