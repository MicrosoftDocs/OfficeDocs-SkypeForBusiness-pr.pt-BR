---
title: 'Lync Server 2013: integrando com o Microsoft Exchange Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Exchange Server 2013
ms:assetid: 795dc1c6-524f-4012-8b66-103b55198044
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688098(v=OCS.15)
ms:contentKeyID: 49733697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1467f6a570f83908eb5809f9493303bdc91c169
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-exchange-server-2013"></a>Integração do Microsoft Lync Server 2013 e do Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-07-09_

O Exchange e o Lync Server têm uma longa história de integração e compatibilidade. Essa integração é mais perceptível em seus respectivos aplicativos cliente. Por exemplo, as informações de presença do Lync podem ser reportadas no Microsoft Outlook; da mesma forma, o Lync pode usar o calendário do Outlook para atualizar automaticamente essas informações de presença. (Por exemplo, o Lync pode alterar seu status para ocupado sempre que seu calendário mostrar que você tem uma reunião agendada.) Embora você não precise executar o Exchange para executar o Lync Server (ou vice-versa), há pouco a dúvida de que usar os dois produtos juntos epitomizes a grande definição do termo "melhor juntos".

Isso é especialmente verdadeiro com o lançamento do Microsoft Lync Server 2013 e do Microsoft Exchange Server 2013. Além dos recursos, como mensagens unificadas e mensagens INSTANTÂNEAs e presença, que estão disponíveis no Microsoft Exchange Server 2010 e no Microsoft Lync Server 2010, as versões do 2013 dos produtos do servidor incluem uma série de novos recursos. Esses recursos incluem itens como:

  - **Integração de arquivamento do Lync**. No Lync Server 2013, os administradores ainda têm a opção de ter mensagens instantâneas e transcrições de Webconferência arquivadas no SQL Server (da mesma forma como essas transcrições foram arquivadas no Lync Server 2010). Como alternativa, no entanto, os administradores podem optar por fazer transcrições arquivadas no Exchange 2013, armazenando essas transcrições nas caixas de correio de usuário individuais da mesma forma que o Exchange arquiva comunicações. Isso significa um único repositório para todas as suas comunicações eletrônicas (do Exchange e do Lync Server), o que torna muito mais fácil pesquisar e recuperar essas comunicações arquivadas caso a necessidade seja necessária.

  - **Repositório de contatos unificado**. No Lync Server 2010, os usuários tinham que manter listas de contatos separadas no Outlook e no Lync; na verdade, para garantir que você tinha os mesmos contatos disponíveis nos dois produtos que você tinha para manter as listas de contatos duplicadas, uma para o Outlook e outra para o Lync. No Lync Server 2013, no entanto, os contatos do usuário podem ser armazenados no Exchange 2013 e no repositório de contatos unificado. Usar um único repositório de contatos permite que os usuários mantenham apenas um conjunto de contatos, com o mesmo conjunto de contatos disponível no Lync 2013, no Outlook 2013 e no Outlook Web Access 2013.

  - **Agendamento de reunião do Lync do OWA**. Com a integração do Lync Server 2013 e do Exchange 2013, os usuários podem agendar reuniões do Lync a partir do Outlook Web Access 2013.

  - **Fotos de alta resolução**. O Lync 2010 pode exibir apenas fotos pequenas de seus contatos; Isso ocorre porque essas fotos foram armazenadas no Active Directory e o Active Directory impõe um 48 pixel por 48 limite de tamanho de pixel em fotos armazenadas. No Lync Server 2013, no entanto, as fotos podem ser armazenadas no Microsoft Exchange; Isso permite fotos de alta resolução tão grandes quanto 648 pixels por 648 pixels. Como você pode esperar, o Lync 2013 foi atualizado para permitir a exibição dessas fotografias de alta resolução.

Lembre-se de que esses novos recursos exigem o uso do Lync Server 2013 e do Exchange 2013. Além disso, os usuários que esperam aproveitar todos esses novos recursos devem ter contas no Lync Server 2013 e no Exchange 2013 e devem estar usando as versões mais recentes do software cliente (por exemplo, Lync 2013). Por exemplo, o repositório de contatos unificado não está disponível para os usuários que foram hospedados no Lync Server 2010; da mesma forma, fotos de alta resolução não podem ser exibidas no Lync 2010.

Esta documentação fornece informações sobre a integração do Lync Server 2013 e do Exchange 2013. incluindo informações passo a passo sobre como habilitar novos recursos, como integração de arquivamento e repositório de contatos unificado. O que essa documentação não faz é discutir a configuração e a configuração iniciais desses dois produtos. Para obter detalhes sobre a implantação do Lync Server 2013, consulte o Lync Server 2013 [http://go.microsoft.com/fwlink/p/?LinkId=246127](http://go.microsoft.com/fwlink/p/?linkid=246127)Tech Center em. Para obter detalhes sobre a implantação do Exchange 2013, consulte o Exchange 2013 [http://go.microsoft.com/fwlink/p/?LinkId=268528](http://go.microsoft.com/fwlink/p/?linkid=268528)Tech Center em.

<div>

## <a name="in-this-section"></a>Nesta seção

[Pré-requisitos para a integração do Microsoft Lync Server 2013 e do Microsoft Exchange Server 2013](lync-server-2013-prerequisites-for-integrating-with-exchange-server-2013.md)

[Configurando aplicativos de parceiros no Microsoft Lync Server 2013 e no Microsoft Exchange Server 2013](lync-server-2013-configuring-partner-applications-in-lync-server-2013-and-exchange-server-2013.md)

[Configurando o Microsoft Lync Server 2013 para usar o Microsoft Exchange Server 2013 Archiving](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md)

[Configurando o Microsoft SharePoint Server 2013 para pesquisar dados do Microsoft Lync Server 2013 arquivados](lync-server-2013-configuring-microsoft-sharepoint-server-2013-to-search-for-archived-lync-server-2013-data.md)

[Configurando o Microsoft Lync Server 2013 para usar o repositório de contatos unificado](lync-server-2013-configuring-lync-server-to-use-the-unified-contact-store.md)

[Configurando o uso de fotos de alta resolução no Microsoft Lync Server 2013](lync-server-2013-configuring-the-use-of-high-resolution-photos.md)

[Configurando o Microsoft Exchange Server 2013 Unified Messaging para o Microsoft Lync Server 2013 voice mail](lync-server-2013-configuring-microsoft-exchange-server-2013-unified-messaging-for-lync-server-2013-voice-mail.md)

[Integração do Microsoft Lync Server 2013 e do Microsoft Outlook Web App 2013](lync-server-2013-integrating-lync-server-and-outlook-web-app-2013.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

