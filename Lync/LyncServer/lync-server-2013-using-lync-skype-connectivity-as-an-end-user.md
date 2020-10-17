---
title: 'Lync Server 2013: usando a conectividade Lync-Skype como um usuário final'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Lync-Skype connectivity as an end user
ms:assetid: ad22f731-118c-4349-8790-b1a72941cbdd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn440175(v=OCS.15)
ms:contentKeyID: 57793365
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94bb9a2d5fa584de5b6195de0ad2accf6899d0e7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535768"
---
# <a name="using-lync-skype-connectivity-in-lync-server-2013-as-an-end-user"></a>Usando a conectividade Lync-Skype no Lync Server 2013 como um usuário final

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2016-12-27_

Lync-Skype conectividade permite que usuários do Skype e usuários do Lync adicionem uns aos outros como contatos, mensagens instantâneas do Exchange e façam chamadas de áudio e vídeo. Quando um usuário do Skype adiciona um usuário do Lync, um usuário do Skype cria um contato no Skype contendo o URI (Uniform Resource Identifier) do protocolo SIP do usuário do Lync. Por outro lado, quando um usuário do Lync adiciona um contato do Skype, o usuário do Lync criará um contato no Lync que conterá a conta da Microsoft (MSA) do usuário do Skype e não o nome de usuário do Skype.

**O que é um MSA?** Os usuários do Skype devem entrar no Skype com uma conta da Microsoft (anteriormente denominada Windows Live ID) para se comunicar com contatos do Lync.Uma conta da Microsoft consiste na combinação de um endereço de email e uma senha, que você também pode usar para entrar em serviços como a tecnologia de armazenamento do Microsoft OneDrive, o Windows Phone, o serviço de jogos do Microsoft Xbox LIVE online e o cliente de mensagens e colaboração do Microsoft Outlook (e, anteriormente, o serviço de email baseado na Web do Microsoft Hotmail ou o Windows Live Messenger).Se você usar um endereço de email e uma senha para se conectar a esses ou outros serviços, você já tem uma conta da Microsoft.Para obter detalhes sobre como criar uma conta da Microsoft, consulte a página de inscrição da conta da Microsoft em [https://go.microsoft.com/fwlink/p/?LinkId=306061](https://go.microsoft.com/fwlink/p/?linkid=306061) . Você pode mesclar sua conta do Skype existente com sua conta da Microsoft para logon único, em vários aplicativos e serviços. Depois que a conta for mesclada, um usuário do Skype poderá enviar uma solicitação de contato aos usuários do Lync.

<div>


> [!IMPORTANT]  
> Para que os usuários do Lync e do Skype se comuniquem entre si, os seguintes requisitos devem ser atendidos: 
> <UL>
> <LI>
> <P>Os usuários do Skype devem estar conectados ao cliente Skype com uma conta da Microsoft (MSA).</P>
> <LI>
> <P>Os usuários do Lync devem estar habilitados para conectividade de IM pública pelo administrador do Lync.</P>
> <LI>
> <P>Quando um usuário do Skype adiciona um contato do Lync, verifique se o Word Lync aparece abaixo do nome do contato. Isso indica que um URI do Lync foi encontrado.</P>
> <LI>
> <P>Quando um usuário do Skype adiciona um contato do Lync e resultados de pesquisa zero são retornados para esse domínio do Lync, o processo de provisionamento PIC pode não ter sido concluído ou o domínio do Lync ainda não foi configurado.</P>
> <LI>
> <P>Dependendo das configurações de privacidade dos usuários do Lync e do Skype, IM, vídeo e presença podem não funcionar até que os novos contatos sejam aceitos por cada usuário.</P></LI></UL>



</div>

**Para adicionar um contato do Skype ao Lync 2013**

1.  No Lync, clique em **Adicionar um contato, adicionar um contato que não está na minha organização**.

2.  Na lista de provedores de contato disponíveis, selecione **Skype**.

3.  No campo **endereço de mensagens instantâneas** , insira a conta da Microsoft (MSA) do usuário do Skype.

4.  Na caixa suspensa **Adicionar a grupo de contatos** , selecione um grupo de contatos ao qual adicionar o usuário.

5.  Na caixa de lista suspensa **definir relação de privacidade** , selecione a configuração de contato apropriada e clique em **OK**.

6.  Agora, o usuário será exibido como um contato no Lync. Selecione o usuário, clique com o botão direito do mouse no nome do usuário e clique em **Ver cartão de visita** para exibir as propriedades do usuário. Agora você pode estabelecer uma chamada de áudio ou vídeo com o usuário do Skype recentemente adicionado.

Para obter informações adicionais sobre o suporte para contatos, consulte [Adicionar um contato no Lync](https://support.office.com/article/add-a-contact-ae55b88d-b9af-48da-bffe-7cc720a5059a).

Quando uma conta da Microsoft do usuário do Skype usa um nome de domínio personalizado, como o <strong>Bob@contoso.com</strong> , um usuário do Lync pode adicionar essa conta da Microsoft ao Lync de duas maneiras:

1.  Use o ícone **Adicionar um contato** ou

2.  Use o campo **localizar alguém ou uma sala, ou um campo discar um número** .

Em cada instância, o usuário do Lync deve inserir o email do usuário do Skype no seguinte formato: <strong>usuário (nome de domínio) @msn. com</strong> .

<div>


> [!IMPORTANT]  
> Esta etapa não é necessária para contas da Microsoft que usam os seguintes nomes de domínio: <STRONG>@live. com, @hotmail. com ou @outlook. com</STRONG>. Para obter mais informações sobre nomes de domínio personalizados com suporte, consulte <A href="https://support.microsoft.com/kb/897567">domínios de mensagens instantâneas públicas compatíveis</A>.



</div>

**Para adicionar um contato do Skype ao Lync ao usar um nome de domínio personalizado**

1.  No Lync, clique em **Adicionar um contato, adicionar um contato que não está na minha organização**.

2.  Na lista de provedores de contato disponíveis, selecione **Skype**.

3.  No campo **endereço de mensagens instantâneas** , insira a conta da Microsoft (MSA) do usuário do Skype no formato <strong>usuário (nome de domínio) @msn. com</strong>. Portanto, para o usuário bob@contoso.com, a entrada seria <strong> Bob (contoso. com) @msn. com <strong> .

4.  Na caixa de listagem suspensa **Adicionar ao grupo de contatos** , selecione um grupo de contatos ao qual adicionar o usuário.

5.  Na caixa de listagem suspensa **definir relação de privacidade** , selecione a configuração de contato apropriada e clique em **OK**.

6.  Um usuário do Lync também pode usar a **localização de alguém ou uma sala, ou discar um** campo de número no Lync e adicionar um endereço semelhante ao seguinte <strong>usuário (nome de domínio) @msn. com</strong> . Portanto, para a conta da Microsoft bob@contoso.com, a entrada seria <strong>Bob (contoso. com) @msn. com</strong> .

7.  Siga as etapas 4 e 5 anteriormente neste procedimento para adicionar o contato a um grupo de contatos e selecionar a relação de privacidade apropriada.

**Para adicionar um contato do Lync ao Skype**

1.  Entrar no Skype. O usuário do Skype deve estar conectado ao cliente Skype com uma conta da Microsoft (MSA).

2.  Selecione o ícone adicionar contatos.

3.  Insira o URI do SIP do usuário do Lync. Por exemplo, bob@contoso.com.

4.  Quando o Skype encontrar a correspondência nos resultados da pesquisa, procure o Word **Lync** abaixo do nome do usuário do Lync. Isso indica que o Skype localizou com êxito o URI SIP do cliente do Lync. Clique no nome.

5.  No canto superior direito da janela, clique em Adicionar a contatos.

6.  Agora, o novo contato será adicionado à sua lista de contatos, mas você verá um ponto de interrogação em vez do ícone de status até que aceite sua solicitação. Quando o novo contato aceitar sua solicitação, você poderá ver quando elas estão online, iniciar conversas de IM e fazer chamadas de áudio e vídeo.
    
    <div>
    

    > [!IMPORTANT]  
    > O administrador do Lync Server deve definir as configurações de política do usuário do Lync para permitir as solicitações de entrada. Caso contrário, o usuário do Lync não receberá solicitações de contato do usuário do Skype. Dependendo da configuração das configurações de política do usuário do Lync, a solicitação para adicionar o usuário do Skype será exibida na guia <STRONG>novo</STRONG> do cliente Lync. Para começar a comunicar com o usuário do Skype, o usuário do Lync deve adicionar o usuário do Skype à lista de favoritos ou uma lista de contatos. A imagem abaixo mostra o local da <STRONG>nova</STRONG> guia no cliente do Lync.

    
    </div>

Um usuário do Lync deve configurar alertas do Lync para garantir que as solicitações enviadas de um usuário do Skype apareçam e sejam detectáveis pelo usuário do Lync. Para configurar alertas do Lync, conclua o procedimento a seguir.

**Para configurar alertas do Lync**

1.  No cliente Lync, clique no ícone **Opções** .

2.  Selecione **alertas**.

3.  Em **alertas gerais**, confira avisar **quando alguém me adicionar à sua lista de contatos**.

4.  Em **contatos não usando o Lync**, selecione **permitir convites, mas bloquear todas as outras comunicações**.

5.  Clique em **OK** para fechar a janela Opções.

</div>

<span> </span>

</div>

</div>

</div>

