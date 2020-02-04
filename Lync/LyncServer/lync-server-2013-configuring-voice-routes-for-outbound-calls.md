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
ms.openlocfilehash: f8b425ce1e0627645f84223f36f6fc0de18b5af8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734391"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-voice-routes-for-outbound-calls-in-lync-server-2013"></a>Configurando rotas de voz para chamadas de saída no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Uma rota de voz do Lync Server 2013 associa números de telefone de destino a um ou mais gateways de rede telefônica pública comutada (PSTN) ou troncos SIP e um ou mais registros de uso de PSTN.

**Para exibir as rotas de voz usando o painel de controle do Lync Server**

1.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Clique em **Roteamento de voz**.

3.  Clique em **Rota**.

4.  Clique duas vezes em uma rota de voz para ver as propriedades adicionais da lista de rotas de voz ou selecione o roteiro e clique em **Editar**. Em seguida, clique em **Mostrar detalhes**.
    
    <div>
    

    > [!NOTE]  
    > Você só pode exibir informações detalhadas sobre uma única rota de cada vez.

    
    </div>

**Para exibir as rotas de voz usando o Windows PowerShell**

  - Inicie o Shell de gerenciamento do Lync Server: clique em **Iniciar**, em **todos os programas**, em **Microsoft Lync Server 2013**e, em seguida, clique em **Shell de gerenciamento do Lync Server**. As rotas de voz podem ser visualizadas usando o Windows PowerShell e o cmdlet **Get-CsVoiceRoute** . Esse cmdlet pode ser executado no Shell de gerenciamento do Lync Server 2013 ou em uma sessão remota do Windows PowerShell. Para obter detalhes sobre como usar o Windows PowerShell remoto para se conectar ao Lync Server, consulte o artigo sobre o blog do Windows PowerShell do Lync Server "início rápido: gerenciar o [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Microsoft Lync Server 2010 usando o PowerShell remoto" em.
    
    Para ver as informações sobre todas as suas rotas de voz, digite o seguinte comando no Shell de gerenciamento do Lync Server e pressione ENTER:
    
        Get-CsVoiceRoute
    
    Isso retornará informações parecidas com:
    
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

## <a name="see-also"></a>Confira também


[Gerenciando o roteamento de voz no Lync Server 2013](lync-server-2013-managing-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

