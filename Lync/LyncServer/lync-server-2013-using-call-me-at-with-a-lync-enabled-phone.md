---
title: 'Lync Server 2013: usando ligar para mim com um telefone habilitado para Lync'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Call Me At with a Lync-enabled phone
ms:assetid: 975a1df8-a159-4aa4-a991-5972a535998e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn383570(v=OCS.15)
ms:contentKeyID: 56470326
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 157ce646e606f6327e6d7a5fd1957da1480797e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212857"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-call-me-at-with-a-lync-enabled-phone-and-lync-server-2013"></a>Usando ligar para mim com um telefone habilitado para Lync e o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-08-09_

O recurso ligar para mim no Lync oferece uma maneira de os usuários ingressarem na parte de áudio de uma conferência usando um telefone celular, "linha de terreno" ou outro dispositivo conectado à rede telefônica pública comutada (PSTN). Ao tentar ingressar em uma reunião usando o Lync, você normalmente verá a caixa de diálogo **ingressar em áudio de reunião** :

![Usar o Lync para participar da captura de tela da janela de áudio da reunião](images/Dn383570.e28f17f0-9f17-44ef-b893-f4ef132f47ac(OCS.15).png "Usar o Lync para participar da captura de tela da janela de áudio da reunião")

Se você selecionar **ligar para mim**, poderá escolher um número de telefone na lista suspensa. O Lync Server 2013 fará uma chamada telefônica para o número selecionado e você poderá usar esse telefone para participar da parte de áudio da conferência.

A lista suspensa é preenchida pelos números de telefone (para celular, telefone residencial ou outro telefone) digitado na guia **telefones** da caixa de diálogo **Lync – opções** :

![Captura de tela de opções de configuração do Lync phones](images/Dn383570.03d2f25d-49e2-47b4-b1e9-b1614fc0c11c(OCS.15).png "Captura de tela de opções de configuração do Lync phones")

Se você não tiver inserido números de telefone na guia **telefones** , não haverá números disponíveis na caixa suspensa. No entanto, você sempre pode clicar em **novo número** e fazer o Lync Server discar para qualquer número de telefone que desejar:

![Captura de tela do Lync ingressar em áudio de reuniões](images/Dn383570.27f2ac7a-cc1c-465c-b145-202ad03af4f2(OCS.15).png "Captura de tela do Lync ingressar em áudio de reuniões")

O recurso ligar para mim funciona muito bem, desde que você o use da forma como era destinado: fazendo com que o Lync Server chame um número de telefone PSTN. No entanto, você pode executar uma experiência inferior à ideal se solicitar que o Lync Server chame você em um ponto de extremidade habilitado para Lync (por exemplo, um telefone em uma sala de conferência). Veja a seguir o problema que você pode executar, além de duas maneiras de contornar o problema.

Para começar, veja o que acontece quando você fornece o recurso ligar para mim com o número de telefone de um telefone habilitado para Lync. Suponha que Ken Myer tente ingressar em uma reunião com o Lync Server chamá-lo em 1-206-555-1219, um número de telefone habilitado para Lync Server. Ken será inicialmente conectado à reunião, mas, após alguns segundos, o Lync exibirá a chamada de mensagem **não foi concluída ou terminou**, e Ken parecerá ter sido descartado da reunião:

![Captura de tela da janela de conferência de chamada do Lync](images/Dn383570.c2a81727-8751-41b5-946a-03a1b75b9d95(OCS.15).png "Captura de tela da janela de conferência de chamada do Lync")

No entanto, observe que há uma discrepância dentro da janela de conversa do Lync. Ken Myer é o único nome listado no título dos **participantes** . No entanto, se você procurar na barra de título da janela, verá que a conferência contém um total de quatro participantes.

Da mesma forma, se você examinar a janela de conversa de qualquer um dos outros participantes da conferência, não verá Ken Myer listado em qualquer lugar:

![Captura de tela da janela de lista de participantes do Lync](images/Dn383570.fa5990cf-2694-402c-ac06-946aa66b6837(OCS.15).png "Captura de tela da janela de lista de participantes do Lync")

E ainda, ao mesmo tempo, Ken Myer poderá participar da parte de áudio da chamada usando o telefone habilitado para Lync. Na verdade, o recurso ligar para mim funcionou, mas a experiência do usuário é inferior à ideal.

Há pelo menos duas maneiras de contornar esse problema. Se você já tiver ingressado em uma conferência dessa maneira (como Ken Myer DID), normalmente poderá resolver o problema ao envolver uma modalidade diferente. Por exemplo, se você enviar uma mensagem instantânea, a janela de conversa agora mostrará todos os participantes da conferência, incluindo você mesmo:

![Captura de tela de conversa do Lync e lista de participantes](images/Dn383570.9b5ff6d6-9f73-467c-99a7-ef3aa8bd7e7a(OCS.15).png "Captura de tela de conversa do Lync e lista de participantes")

Neste ponto, você deve ser capaz de participar da reunião no modo esperado.

Como alternativa, você pode evitar esse problema completamente alterando a forma como ingressar na reunião. Se você precisar que a chamada do Lync Server seja um telefone habilitado para Lync Server, comece a ingressar na reunião sem uma conexão de áudio. Para fazer isso, selecione não ingressar no áudio quando aparecer a caixa de diálogo ingressar em áudio da reunião:

![Lync não ingressar na tela de áudio da janela](images/Dn383570.280a148d-cce5-4b02-87f9-9f78f17a81c1(OCS.15).png "Lync não ingressar na tela de áudio da janela")

Após a conexão com êxito à reunião, agora você pode "convidar" o telefone habilitado para Lync Server para ingressar na reunião também. Para fazer isso, coloque o mouse sobre o ícone de pessoas e clique em **convidar mais pessoas**:

![Captura de tela da janela de convite mais participantes do Lync](images/Dn383570.69b81b29-d1d2-4ed3-acb6-e37dd18e3d86(OCS.15).png "Captura de tela da janela de convite mais participantes do Lync")

Isso exibirá a caixa de diálogo **Enviar uma mensagem instantânea** . Ignore o título da caixa de diálogo (você não está realmente enviando uma mensagem instantânea) e digite o número de telefone do telefone habilitado para Lync:

![Enviar uma captura de tela de caixa de diálogo de IM](images/Dn383570.cd67a3f0-06d8-41ba-a808-c067f64bec9f(OCS.15).png "Enviar uma captura de tela de caixa de diálogo de IM")

Depois que você clicar em **OK**, o Lync Server chamará o número inserido na caixa de diálogo. Quando a conexão for feita, você terá recursos de áudio completo por meio do telefone habilitado para Lync e poderá ver e interagir com a lista completa de conferência.

</div>

<span> </span>

</div>

</div>

</div>

