---
title: 'Lync Server 2013: Configurando rotas de voz para chamadas de saída'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring voice routes for outbound calls
ms:assetid: 3c182cdd-7a4a-4a9d-bdac-4199f0abd947
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425890(v=OCS.15)
ms:contentKeyID: 48183875
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c5c74a11adfb3785196352f3c03772028e73ec9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Configurando rotas de voz para chamadas de saída no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Uma rota de voz do Lync Server 2013 associa números de telefone de destino com um ou mais gateways PSTN (rede telefônica pública comutada) ou troncos SIP e um ou mais registros de uso de PSTN.

**Para exibir rotas de voz usando o painel de controle do Lync Server**

1.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Clique em **Roteamento de voz**.

3.  Clique em **Rota**.

4.  Clique duas vezes em uma rota de voz para visualizar propriedades adicionais a partir da lista de rotas de voz ou selecione a rota e clique em **Editar**. Então, clique em **Exibir detalhes**.
    
    <div>
    

    > [!NOTE]  
    > Você só pode visualizar informações detalhadas para uma única rota por vez.

    
    </div>

**Para exibir rotas de voz usando o Windows PowerShell**

  - Inicie o Shell de Gerenciamento do Lync Server: clique em **Iniciar**, em **Todos os Programas**, em **Microsoft Lync Server 2013** e em **Shell de Gerenciamento do Lync Server**. As rotas de voz podem ser visualizadas usando o Windows PowerShell e o cmdlet **Get-CsVoiceRoute** . Este cmdlet pode ser executado a partir do Shell de gerenciamento do Lync Server 2013 ou de uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo de blog do Lync Server Windows PowerShell "início rápido: Managing Microsoft Lync Server [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)2010 using Remote PowerShell" em.
    
    Para exibir informações sobre todas as suas rotas de voz, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsVoiceRoute
    
    Isto retorna informações semelhantes à seguinte:
    
        Identity          : global
        Priority          : -1
        Description       :
        NumberPattern     : ^(\+1[0-9]{10})$
        PstnUsages        : {}
        PstnGatewayList   : {}
        Name              : global
        SuppressCallerId  :
        AlternateCallerId :

<div>


> [!NOTE]  
> Para obter detalhes, consulte <A href="lync-server-2013-voice-routes.md">rotas de voz no Lync Server 2013</A> na documentação de planejamento.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md)

  - [Modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md)

</div>

<div>

## <a name="see-also"></a>Confira Também


[Gerenciando o roteamento de voz no Lync Server 2013](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

