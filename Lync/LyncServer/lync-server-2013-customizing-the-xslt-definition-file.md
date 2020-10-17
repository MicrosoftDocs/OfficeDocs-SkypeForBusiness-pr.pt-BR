---
title: 'Lync Server 2013: Personalizando o arquivo de definição XSLT'
description: 'Lync Server 2013: Personalizando o arquivo de definição XSLT.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Customizing the XSLT definition file
ms:assetid: f18dd78c-3598-4f38-b496-96b750c6e518
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679898(v=OCS.15)
ms:contentKeyID: 49557733
ms.date: 09/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b248b44c9257fa9f30cc99a3773abf71ddbd8651
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553797"
---
# <a name="customizing-the-xslt-definition-file-in-lync-server-2013"></a><span data-ttu-id="dfa85-103">Personalizando o arquivo de definição do XSLT no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfa85-103">Customizing the XSLT definition file in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfa85-104">_**Última modificação do tópico:** 2014-09-11_</span><span class="sxs-lookup"><span data-stu-id="dfa85-104">_**Topic Last Modified:** 2014-09-11_</span></span>

<span data-ttu-id="dfa85-105">O serviço de conformidade registra e arquiva dados relacionados a cada Lync Server 2013, conversa de servidor de chat persistente, incluindo quando um participante:</span><span class="sxs-lookup"><span data-stu-id="dfa85-105">The Compliance service records and archives data related to each Lync Server 2013, Persistent Chat Server conversation, including when a participant:</span></span>

  - <span data-ttu-id="dfa85-106">Ingressa em uma sala de chat persistente</span><span class="sxs-lookup"><span data-stu-id="dfa85-106">Joins a Persistent Chat room</span></span>

  - <span data-ttu-id="dfa85-107">Sai de uma sala de chat</span><span class="sxs-lookup"><span data-stu-id="dfa85-107">Leaves a chat room</span></span>

  - <span data-ttu-id="dfa85-108">Posta uma mensagem</span><span class="sxs-lookup"><span data-stu-id="dfa85-108">Posts a message</span></span>

  - <span data-ttu-id="dfa85-109">Exibe o histórico do chat</span><span class="sxs-lookup"><span data-stu-id="dfa85-109">Views chat history</span></span>

  - <span data-ttu-id="dfa85-110">Carrega um arquivo</span><span class="sxs-lookup"><span data-stu-id="dfa85-110">Uploads a file</span></span>

  - <span data-ttu-id="dfa85-111">Baixa um arquivo</span><span class="sxs-lookup"><span data-stu-id="dfa85-111">Downloads a file</span></span>

<span data-ttu-id="dfa85-p101">Os dados são entregues como XML, que você pode transformar no formato mais adequado para a sua organização, usando um arquivo de definição XSLT. Este tópico descreve o arquivo XML que o serviço de Conformidade cria. Ele também fornece exemplos de arquivos de saída e definição XSLT.</span><span class="sxs-lookup"><span data-stu-id="dfa85-p101">The data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file. This topic describes the XML file that the Compliance service creates. It also provides samples of XSLT definition and output files.</span></span>

<div>

## <a name="output-format"></a><span data-ttu-id="dfa85-115">Formato de saída</span><span class="sxs-lookup"><span data-stu-id="dfa85-115">Output Format</span></span>

<span data-ttu-id="dfa85-116">A saída do serviço de Conformidade é categorizada por conversa (o elemento Conversation) e depois por mensagem (o elemento Messages), conforme mostrado no exemplo de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="dfa85-116">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample.</span></span>

    <?xml version="1.0" encoding="utf-8" ?> 
    <Conversations xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xsd="http://www.w3.org/2001/XMLSchema">
      <Conversation>
        <Channel uri="ma-chan://litwareinc.com/300" name="ma-chan://litwareinc.com/300" islogged="" /> 
        <!--FirstMessage goes here --!>
        <Messages> 
          <!—Messages go here--!>
        </Messages>
        <StartTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
        <EndTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
      </Conversation>
    </Conversations>

<span data-ttu-id="dfa85-p102">Um elemento Conversation contém quatro elementos (Channel, FirstMessage, StartTimeUTC e EndTimeUTC). O elemento Channel contém o URI (Uniform Resource Identifier) da sala de chat, e o elemento FirstMessage descreve a primeira mensagem no elemento Messages. Os elementos StartTimeUTC e EndTimeUTC fornecem os horários de início e término da conversa, como mostrado no exemplo de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="dfa85-p102">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC). The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element. The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample.</span></span>

    <<FirstMessage type="JOIN" content="" id="0">
          <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
          <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
    </FirstMessage>

<span data-ttu-id="dfa85-p103">Um elemento Message contém dois elementos (Sender e DateTimeUTC) e três atributos (Type, Content e ID). O elemento Sender representa o usuário que envia a mensagem e o elemento DateTimeUTC representa quando ocorre um evento, conforme mostrado no exemplo de código a seguir.</span><span class="sxs-lookup"><span data-stu-id="dfa85-p103">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID). The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample.</span></span>

    <Message type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
    </Message>

<span data-ttu-id="dfa85-122">Os atributos de mensagem Type, Content e ID são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="dfa85-122">The following table describes the message attributes Type, Content, and ID.</span></span>

### <a name="messages-element-attributes"></a><span data-ttu-id="dfa85-123">Atributos do elemento Messages</span><span class="sxs-lookup"><span data-stu-id="dfa85-123">Messages Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfa85-124">Atributo</span><span class="sxs-lookup"><span data-stu-id="dfa85-124">Attribute</span></span></th>
<th><span data-ttu-id="dfa85-125">Descrição</span><span class="sxs-lookup"><span data-stu-id="dfa85-125">Description</span></span></th>
<th><span data-ttu-id="dfa85-126">Opcional/obrigatório</span><span class="sxs-lookup"><span data-stu-id="dfa85-126">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfa85-127">Tipo</span><span class="sxs-lookup"><span data-stu-id="dfa85-127">Type</span></span></p></td>
<td><p><span data-ttu-id="dfa85-p104">Especifica o tipo de mensagem. Os tipos de mensagens são descritos na tabela Tipos de mensagem dos elementos Messages.</span><span class="sxs-lookup"><span data-stu-id="dfa85-p104">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span></p></td>
<td><p><span data-ttu-id="dfa85-130">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="dfa85-130">Required</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfa85-131">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="dfa85-131">Content</span></span></p></td>
<td><p><span data-ttu-id="dfa85-p105">Contém o conteúdo da mensagem. As mensagens com um tipo Ingressar ou Participar não usam esse atributo.</span><span class="sxs-lookup"><span data-stu-id="dfa85-p105">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span></p></td>
<td><p><span data-ttu-id="dfa85-134">Opcional</span><span class="sxs-lookup"><span data-stu-id="dfa85-134">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfa85-135">ID</span><span class="sxs-lookup"><span data-stu-id="dfa85-135">ID</span></span></p></td>
<td><p><span data-ttu-id="dfa85-p106">Especifica a identificação exclusiva do conteúdo. Esse atributo é usado somente com mensagens com um tipo Chat.</span><span class="sxs-lookup"><span data-stu-id="dfa85-p106">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span></p></td>
<td><p><span data-ttu-id="dfa85-138">Opcional</span><span class="sxs-lookup"><span data-stu-id="dfa85-138">Optional</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dfa85-p107">Cada elemento Sender contém cinco atributos: nome de usuário, identificação, email, interno e URI. Esses atributos são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="dfa85-p107">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>

### <a name="sender-element-attributes"></a><span data-ttu-id="dfa85-141">Atributos do elemento Sender</span><span class="sxs-lookup"><span data-stu-id="dfa85-141">Sender Element Attributes</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfa85-142">Atributo</span><span class="sxs-lookup"><span data-stu-id="dfa85-142">Attribute</span></span></th>
<th><span data-ttu-id="dfa85-143">Descrição</span><span class="sxs-lookup"><span data-stu-id="dfa85-143">Description</span></span></th>
<th><span data-ttu-id="dfa85-144">Opcional/obrigatório</span><span class="sxs-lookup"><span data-stu-id="dfa85-144">Optional/Required</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfa85-145">Nome de usuário</span><span class="sxs-lookup"><span data-stu-id="dfa85-145">Username</span></span></p></td>
<td><p><span data-ttu-id="dfa85-146">O nome do remetente.</span><span class="sxs-lookup"><span data-stu-id="dfa85-146">The name of the sender.</span></span></p></td>
<td><p><span data-ttu-id="dfa85-147">Opcional</span><span class="sxs-lookup"><span data-stu-id="dfa85-147">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfa85-148">ID</span><span class="sxs-lookup"><span data-stu-id="dfa85-148">ID</span></span></p></td>
<td><p><span data-ttu-id="dfa85-149">A ID exclusiva do remetente.</span><span class="sxs-lookup"><span data-stu-id="dfa85-149">The sender’s unique ID.</span></span></p></td>
<td><p><span data-ttu-id="dfa85-150">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="dfa85-150">Required</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfa85-151">Email</span><span class="sxs-lookup"><span data-stu-id="dfa85-151">Email</span></span></p></td>
<td><p><span data-ttu-id="dfa85-152">O endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="dfa85-152">The sender’s email address.</span></span></p></td>
<td><p><span data-ttu-id="dfa85-153">Opcional</span><span class="sxs-lookup"><span data-stu-id="dfa85-153">Optional</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfa85-154">Interno</span><span class="sxs-lookup"><span data-stu-id="dfa85-154">Internal</span></span></p></td>
<td><p><span data-ttu-id="dfa85-p108">Determina se o usuário é um usuário interno ou um usuário federado. Se o valor for definido como true, o usuário será interno.</span><span class="sxs-lookup"><span data-stu-id="dfa85-p108">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span></p></td>
<td><p><span data-ttu-id="dfa85-157">Opcional</span><span class="sxs-lookup"><span data-stu-id="dfa85-157">Optional</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfa85-158">Uri</span><span class="sxs-lookup"><span data-stu-id="dfa85-158">Uri</span></span></p></td>
<td><p><span data-ttu-id="dfa85-159">A URI SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="dfa85-159">The user’s SIP URI.</span></span></p></td>
<td><p><span data-ttu-id="dfa85-160">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="dfa85-160">Required</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="dfa85-p109">A tabela a seguir descreve os tipos de mensagem que o elemento Messages pode conter. Ela também fornece exemplos de como cada elemento é usado.</span><span class="sxs-lookup"><span data-stu-id="dfa85-p109">The following table describes the message types that the Messages element can contain. It also provides examples of how each element is used.</span></span>

### <a name="message-element-message-types"></a><span data-ttu-id="dfa85-163">Tipos de mensagem do elemento Message</span><span class="sxs-lookup"><span data-stu-id="dfa85-163">Message Element Message Types</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dfa85-164">Tipo de mensagem</span><span class="sxs-lookup"><span data-stu-id="dfa85-164">Message Type</span></span></th>
<th><span data-ttu-id="dfa85-165">Descrição</span><span class="sxs-lookup"><span data-stu-id="dfa85-165">Description</span></span></th>
<th><span data-ttu-id="dfa85-166">Exemplo de código</span><span class="sxs-lookup"><span data-stu-id="dfa85-166">Code example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dfa85-167">Ingressar</span><span class="sxs-lookup"><span data-stu-id="dfa85-167">Join</span></span></p></td>
<td><p><span data-ttu-id="dfa85-168">Um usuário ingressa em uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="dfa85-168">A user joins a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;JOIN&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206211842612&quot; string=&quot;2008-03-22T18:50:42.6127374Z&quot; long=&quot;633418086426127374&quot; /&gt; 
&lt;/Message</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfa85-169">Parte</span><span class="sxs-lookup"><span data-stu-id="dfa85-169">Part</span></span></p></td>
<td><p><span data-ttu-id="dfa85-170">Um usuário sai de uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="dfa85-170">A user leaves a chat room.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;PART&quot; content=&quot;&quot; id=&quot;0&quot;&gt;
  &lt; Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212610602532&quot; string=&quot;2008-06-04T20:16:42.5324614Z&quot; long=&quot;633482074025324614&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfa85-171">Chat</span><span class="sxs-lookup"><span data-stu-id="dfa85-171">Chat</span></span></p></td>
<td><p><span data-ttu-id="dfa85-172">O endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="dfa85-172">The sender’s email address.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;CHAT&quot; content=&quot;hello&quot; id=&quot;1&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351800522&quot; string=&quot;2008-03-12T19:56:40.522264Z&quot; long=&quot;633409486005222640&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfa85-173">Chat persistente</span><span class="sxs-lookup"><span data-stu-id="dfa85-173">Backchat</span></span></p></td>
<td><p><span data-ttu-id="dfa85-174">Um usuário solicita o conteúdo de histórico do chat.</span><span class="sxs-lookup"><span data-stu-id="dfa85-174">A user requests content from chat history.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;BACKCHAT&quot; content=&quot;backchatcontent&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1206034385284&quot; string=&quot;2008-03-20T17:33:05.2841594Z&quot; long=&quot;633416311852841594&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dfa85-175">Upload de arquivos</span><span class="sxs-lookup"><span data-stu-id="dfa85-175">File upload</span></span></p></td>
<td><p><span data-ttu-id="dfa85-176">Um usuário carrega um arquivo.</span><span class="sxs-lookup"><span data-stu-id="dfa85-176">A user uploads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEUPLOAD&quot; content=&quot;0988239a-bb66-4616-90a4-b07771a2097c.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;TestUser kazuto&quot; id=&quot;10&quot; email=&quot;kazuto@litwareinc.com&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1205351828975&quot; string=&quot;2008-03-12T19:57:08.9755711Z&quot; long=&quot;633409486289755711&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dfa85-177">Download de arquivos</span><span class="sxs-lookup"><span data-stu-id="dfa85-177">File download</span></span></p></td>
<td><p><span data-ttu-id="dfa85-178">Um usuário baixa um arquivo.</span><span class="sxs-lookup"><span data-stu-id="dfa85-178">A user downloads a file.</span></span></p></td>
<td><pre><code>&lt;Message type=&quot;FILEDOWNLOAD&quot; content=&quot;006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt&quot; id=&quot;0&quot;&gt;
  &lt;Sender UserName=&quot;kazuto@litwareinc.com&quot; id=&quot;10&quot; email=&quot;&quot; internal=&quot;true&quot; uri=&quot;kazuto@litwareinc.com&quot; /&gt; 
  &lt;DateTimeUTC since1970=&quot;1212611141851&quot; string=&quot;2008-06-04T20:25:41.8518646Z&quot; long=&quot;633482079418518646&quot; /&gt; 
&lt;/Message&gt;</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="dfa85-179">XSD de saída de chat persistente padrão e transformação XSL de exemplo</span><span class="sxs-lookup"><span data-stu-id="dfa85-179">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="dfa85-180">O exemplo de código a seguir contém a saída padrão do Servidor de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="dfa85-180">The following code sample contains the default output from the Compliance Server.</span></span>

    <?xml version="1.0" encoding="utf-8"?>
    <xs:schema id="Conversations"  xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
       <xs:simpleType name="ComplianceMessageType">
          <xs:restriction base="xs:string">
            <xs:enumeration value="JOIN"/>
            <xs:enumeration value="PART"/>
            <xs:enumeration value="CHAT"/>
            <xs:enumeration value="BACKCHAT"/>
            <xs:enumeration value="FILEUPLOAD"/>
            <xs:enumeration value="FILEDOWNLOAD"/>
          </xs:restriction>
        </xs:simpleType>
      
      <xs:element name="Sender">
        <xs:complexType>
          <xs:attribute name="UserName" type="xs:string" />
          <xs:attribute name="id" type="xs:int" />
          <xs:attribute name="email" type="xs:string" use="optional" />
          <xs:attribute name="internal" type="xs:boolean" use="optional" >
            <xs:annotation><xs:documentation>If the user is internal or federated</xs:documentation></xs:annotation>
          </xs:attribute>
          <xs:attribute name="uri" type="xs:anyURI" use="optional" />
        </xs:complexType>
      </xs:element>
      <xs:element name="DateTimeUTC">
        <xs:complexType>
          <xs:attribute name="since1970" type="xs:long" />
          <xs:attribute name="string" type="xs:string" />
          <xs:attribute name="long" type="xs:long" />
        </xs:complexType>
      </xs:element>
      <xs:element name="Conversations" msdata:IsDataSet="true" msdata:UseCurrentLocale="true">
        <xs:complexType>
          <xs:choice minOccurs="0" maxOccurs="unbounded">
            <xs:element ref="Sender" />
            <xs:element ref="DateTimeUTC" />
            <xs:element name="Conversation">
              <xs:complexType>
                <xs:sequence>
                  <xs:element name="Channel" minOccurs="0" maxOccurs="unbounded">
                    <xs:complexType>
                      <xs:attribute name="uri" type="xs:anyURI" />
                      <xs:attribute name="name" type="xs:string" use="optional" />
                    </xs:complexType>
                  </xs:element>
                  <xs:element name="FirstMessage" minOccurs="0" maxOccurs="unbounded">
                    <xs:complexType>
                      <xs:sequence>
                        <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                        <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                      </xs:sequence>
                      <xs:attribute name="type" type="ComplianceMessageType" />
                      <xs:attribute name="content" type="xs:string" />
                      <xs:attribute name="id" type="xs:int" />
                    </xs:complexType>
                  </xs:element>
                  <xs:element name="Messages" minOccurs="0" maxOccurs="unbounded">
                    <xs:complexType>
                      <xs:sequence>
                        <xs:element name="Message" minOccurs="0" maxOccurs="unbounded">
                          <xs:complexType>
                            <xs:sequence>
                              <xs:element ref="Sender" minOccurs="0" maxOccurs="unbounded" />
                              <xs:element ref="DateTimeUTC" minOccurs="0" maxOccurs="unbounded" />
                            </xs:sequence>
                            <xs:attribute name="type" type="ComplianceMessageType" />
                            <xs:attribute name="content" type="xs:string" />
                            <xs:attribute name="id" type="xs:int" />
                          </xs:complexType>
                        </xs:element>
                      </xs:sequence>
                    </xs:complexType>
                  </xs:element>
                  <xs:element name="StartTimeUTC" minOccurs="0" maxOccurs="unbounded">
                    <xs:complexType>
                      <xs:attribute name="since1970" type="xs:long" />
                      <xs:attribute name="string" type="xs:string" />
                      <xs:attribute name="long" type="xs:long" />
                    </xs:complexType>
                  </xs:element>
                  <xs:element name="EndTimeUTC" minOccurs="0" maxOccurs="unbounded">
                    <xs:complexType>
                      <xs:attribute name="since1970" type="xs:long" />
                      <xs:attribute name="string" type="xs:string" />
                      <xs:attribute name="long" type="xs:long" />
                    </xs:complexType>
                  </xs:element>
                </xs:sequence>
              </xs:complexType>
            </xs:element>
          </xs:choice>
        </xs:complexType>
      </xs:element>
    </xs:schema>

<span data-ttu-id="dfa85-181">O exemplo de código a seguir contém um exemplo de transformação em XSL.</span><span class="sxs-lookup"><span data-stu-id="dfa85-181">The following code sample contains a sample XSL transform.</span></span>

    <xsl:stylesheet version="1.0" xmlns:xsl="http://www.w3.org/1999/XSL/Transform" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:xs="http://www.w3.org/2001/XMLSchema" exclude-result-prefixes="xs">
       <xsl:output method="xml" encoding="UTF-8" indent="yes" />
    
       <xsl:template match="/">
          <FileDump>
             <xsl:apply-templates />
          </FileDump>
       </xsl:template>
    
       <xsl:template match="Conversation">
          <xsl:variable name="chanName" select="Channel/@name" />
          <Conversation Perspective="{$chanName}_group_channel">
             <RoomID><xsl:value-of select="Channel/@name" /></RoomID>
             <StartTimeUTC><xsl:value-of select="StartTimeUTC/@since1970" /></StartTimeUTC>
             <xsl:apply-templates />
             <EndTimeUTC><xsl:value-of select="EndTimeUTC/@since1970" /></EndTimeUTC>
          </Conversation>
       </xsl:template>
    
       <xsl:template match="Message">
          <xsl:choose>
             <xsl:when test="@type='JOIN'">
                <ParticipantEntered>
                   <xsl:call-template name="DateTimeAndLogin" />
                   <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
                   <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
                   <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
                </ParticipantEntered>
             </xsl:when>
    
             <xsl:when test="@type='PART'">
                <ParticipantLeft>
                   <xsl:call-template name="DateTimeAndLogin" />
                   <InternalFlag><xsl:value-of select="Sender/@internal" /></InternalFlag>
                   <ConversationID><xsl:value-of select="../../Channel/@name" /></ConversationID>
                   <CorporateEmailID><xsl:value-of select="Sender/@email" /></CorporateEmailID>
                </ParticipantLeft>
             </xsl:when>
    
             <xsl:when test="@type='FILEUPLOAD' or @type='FILEDOWNLOAD'">
                <FileTransferStarted>
                   <xsl:call-template name="DateTimeAndLogin" />
                   <FileName><xsl:value-of select="@content" /></FileName>
                </FileTransferStarted>
                <FileTransferEnded>
                   <xsl:call-template name="DateTimeAndLogin" />
                   <FileName><xsl:value-of select="@content" /></FileName>
                   <Status>Completed</Status>
                </FileTransferEnded>
             </xsl:when>
    
             <xsl:when test="@type='CHAT' or @type='BACKCHAT'">
                <Message>
                   <xsl:call-template name="DateTimeAndLogin" />
                   <Content><xsl:value-of select="@content" /></Content>
                </Message>
             </xsl:when>
    
             <xsl:otherwise />
          </xsl:choose>
       </xsl:template>
    
       <xsl:template name="DateTimeAndLogin">
          <LoginName><xsl:value-of select="Sender/@userName" /></LoginName>
          <DateTimeUTC><xsl:value-of select="DateTimeUTC/@since1970" /></DateTimeUTC>
       </xsl:template>
    </xsl:stylesheet>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

