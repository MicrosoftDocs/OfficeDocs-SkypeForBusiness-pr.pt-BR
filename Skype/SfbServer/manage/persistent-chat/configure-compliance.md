---
title: Configurar o serviço de Conformidade para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Resumo: Saiba como configurar o serviço de conformidade de servidor de Chat persistente no Skype para Business Server 2015.'
ms.openlocfilehash: 99c09408fbc404edd7ccd6c3844f59dca77a35f0
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568623"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="a74ca-103">Configurar o serviço de Conformidade para o Servidor de Chat Persistente no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a74ca-103">Configure the Compliance service for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a74ca-104">**Resumo:** Saiba como configurar o serviço de conformidade de servidor de Chat persistente no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a74ca-104">**Summary:** Learn how to configure the Persistent Chat Server Compliance service in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a74ca-105">A conformidade de Chat Persistente permite que os administradores mantenham um um arquivo de mensagens de Chat Persistente, bem como de atividades.</span><span class="sxs-lookup"><span data-stu-id="a74ca-105">Persistent Chat compliance lets administrators maintain an archive of Persistent Chat messages as well as activities.</span></span> <span data-ttu-id="a74ca-106">O serviço de conformidade registra e arquiva dados relacionados a cada conversa Persistent Chat Server, incluindo quando um participante:</span><span class="sxs-lookup"><span data-stu-id="a74ca-106">The Compliance service records and archives data related to each Persistent Chat Server conversation, including when a participant:</span></span>
  
- <span data-ttu-id="a74ca-107">Ingressa em uma sala de Chat persistente</span><span class="sxs-lookup"><span data-stu-id="a74ca-107">Joins a Persistent Chat room</span></span>
    
- <span data-ttu-id="a74ca-108">Sai de uma sala de chat</span><span class="sxs-lookup"><span data-stu-id="a74ca-108">Leaves a chat room</span></span>
    
- <span data-ttu-id="a74ca-109">Posta uma mensagem</span><span class="sxs-lookup"><span data-stu-id="a74ca-109">Posts a message</span></span>
    
- <span data-ttu-id="a74ca-110">Exibe o histórico do chat</span><span class="sxs-lookup"><span data-stu-id="a74ca-110">Views chat history</span></span>
    
- <span data-ttu-id="a74ca-111">Carrega um arquivo</span><span class="sxs-lookup"><span data-stu-id="a74ca-111">Uploads a file</span></span>
    
- <span data-ttu-id="a74ca-112">Baixa um arquivo</span><span class="sxs-lookup"><span data-stu-id="a74ca-112">Downloads a file</span></span>
    
<span data-ttu-id="a74ca-113">Essas informações podem ser recuperadas do banco de dados SQL de Conformidade, se necessário.</span><span class="sxs-lookup"><span data-stu-id="a74ca-113">This information can be retrieved from the Compliance SQL database as needed.</span></span> 
  
## <a name="configure-the-compliance-service-by-using-windows-powershell"></a><span data-ttu-id="a74ca-114">Configure o serviço de Conformidade usando o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a74ca-114">Configure the Compliance service by using Windows PowerShell</span></span>

<span data-ttu-id="a74ca-115">Depois que o serviço de Conformidade tiver sido habilitado usando o Construtor de Topologias, você pode configurar o serviço usando o cmdlet **Set-CsPersistenChatComplianceConfiguration**:</span><span class="sxs-lookup"><span data-stu-id="a74ca-115">After the Compliance service has been enabled by using the Topology Builder, you can configure the service by using the **Set-CsPersistenChatComplianceConfiguration** cmdlet:</span></span>
  
```
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

<span data-ttu-id="a74ca-116">ou</span><span class="sxs-lookup"><span data-stu-id="a74ca-116">or</span></span>
  
```
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

<span data-ttu-id="a74ca-117">Você pode definir os seguintes parâmetros:</span><span class="sxs-lookup"><span data-stu-id="a74ca-117">You can set the following parameters:</span></span>
  
- <span data-ttu-id="a74ca-118">AdapterType - Permite que você especifique o tipo de adaptador.</span><span class="sxs-lookup"><span data-stu-id="a74ca-118">AdapterType - Lets you specify the adapter type.</span></span> <span data-ttu-id="a74ca-119">Um adaptador é um produto de terceiros que converte os dados no banco de dados de conformidade para um formato específico.</span><span class="sxs-lookup"><span data-stu-id="a74ca-119">An adapter is a third-party product that converts the data in the compliance database to a specific format.</span></span> <span data-ttu-id="a74ca-120">XML é o padrão.</span><span class="sxs-lookup"><span data-stu-id="a74ca-120">XML is the default.</span></span>
    
- <span data-ttu-id="a74ca-121">OneChatRoomPerOutputFile - esse parâmetro permite que você especifique que separe relatórios a ser criado para cada sala de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="a74ca-121">OneChatRoomPerOutputFile - This parameter lets you specify that separate reports to be created for each chat room.</span></span>
    
- <span data-ttu-id="a74ca-122">AddChatRoomDetails - Quanto habilitado, este parâmetro registra detalhes adicionais sobre cada sala de chat no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a74ca-122">AddChatRoomDetails - When enabled, this parameter records additional details about each chat room in the database.</span></span> <span data-ttu-id="a74ca-123">Como esta configuração pode aumentar consideravelmente o tamanho do banco de dados, ela é desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="a74ca-123">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>
    
- <span data-ttu-id="a74ca-124">AddUserDetails - Quanto habilitado, este parâmetro registra detalhes adicionais sobre cada usuário na sala de chat no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a74ca-124">AddUserDetails - When enabled, this parameter records additional details about each chat room user in the database.</span></span> <span data-ttu-id="a74ca-125">Como esta configuração pode aumentar consideravelmente o tamanho do banco de dados, ela é desabilitada por padrão.</span><span class="sxs-lookup"><span data-stu-id="a74ca-125">Because this setting can greatly increase the size of the database, it is disabled by default.</span></span>
    
- <span data-ttu-id="a74ca-126">Identity - Este parâmetro permite que configurações de conformidade estejam dentro do escopo de uma coleção específica, incluindo níveis de serviço, de site e global.</span><span class="sxs-lookup"><span data-stu-id="a74ca-126">Identity - This parameter allows compliance settings to be scoped for a particular collection, including the global, site, and service levels.</span></span> <span data-ttu-id="a74ca-127">O padrão é o nível global.</span><span class="sxs-lookup"><span data-stu-id="a74ca-127">The default is the global level.</span></span> 
    
- <span data-ttu-id="a74ca-128">RunInterval - Este parâmetro dita o intervalo de tempo antes de o servidor criar o próximo arquivo de saída de conformidade (o padrão é 15 minutos).</span><span class="sxs-lookup"><span data-stu-id="a74ca-128">RunInterval - This parameter dictates the amount of time before the server creates the next compliance output file (the default is 15 minutes).</span></span>
    
## <a name="use-a-customized-compliance-adapter"></a><span data-ttu-id="a74ca-129">Use um adaptador de conformidade personalizado</span><span class="sxs-lookup"><span data-stu-id="a74ca-129">Use a customized compliance adapter</span></span>

<span data-ttu-id="a74ca-130">Você pode escrever um adaptador personalizado em vez de usar o XmlAdapter que é instalado com o servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a74ca-130">You can write a custom adapter instead of using the XmlAdapter that is installed with Persistent Chat Server.</span></span> <span data-ttu-id="a74ca-131">Para fazer isso, você deve fornecer um assembly do .NET Framework que contenha uma classe pública que implemente a interface do **IComplianceAdapter**.</span><span class="sxs-lookup"><span data-stu-id="a74ca-131">To accomplish this, you must provide a .NET Framework assembly that contains a public class that implements the **IComplianceAdapter** interface.</span></span> <span data-ttu-id="a74ca-132">Você deve colocar esse assembly na pasta de instalação do servidor de Chat persistente de cada servidor em seu pool do servidor de Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="a74ca-132">You must place this assembly in the Persistent Chat Server installation folder of each server in your Persistent Chat Server pool.</span></span> <span data-ttu-id="a74ca-133">Qualquer um dos servidores de Conformidade podem fornecer dados de conformidade para seu adaptador, mas os servidores de conformidade não fornecerão dados de conformidade duplicados para várias instâncias do seu adaptador.</span><span class="sxs-lookup"><span data-stu-id="a74ca-133">Any one of the Compliance servers can provide compliance data to your adapter, but the compliance servers will not provide duplicate compliance data to multiple instances of your adapter.</span></span>
  
<span data-ttu-id="a74ca-134">A interface é definida no assembly Compliance.dll no namespace `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span><span class="sxs-lookup"><span data-stu-id="a74ca-134">The interface is defined in the Compliance.dll assembly in the namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance`.</span></span> <span data-ttu-id="a74ca-135">A interface define dois métodos que seu adaptador personalizado deve implementar.</span><span class="sxs-lookup"><span data-stu-id="a74ca-135">The interface defines two methods that your custom adapter must implement.</span></span>
  
<span data-ttu-id="a74ca-136">O servidor de conformidade de Chat persistente chamará o método a seguir quando o adaptador carrega pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="a74ca-136">The Persistent Chat Compliance server will call the following method when the adapter first loads.</span></span> <span data-ttu-id="a74ca-137">O `AdapterConfig` contém a configuração de conformidade de Chat persistente que é relevante para o adaptador de conformidade:</span><span class="sxs-lookup"><span data-stu-id="a74ca-137">The  `AdapterConfig` contains the Persistent Chat compliance configuration that is relevant to the compliance adapter:</span></span>
  
```
void SetConfig(AdapterConfig config)
```

<span data-ttu-id="a74ca-138">O servidor de conformidade de Chat persistente chama o método a seguir em intervalos periódicos desde que há novos dados para traduzir.</span><span class="sxs-lookup"><span data-stu-id="a74ca-138">The Persistent Chat Compliance server calls the following method at periodic intervals as long as there is new data to translate.</span></span> <span data-ttu-id="a74ca-139">Este intervalo de tempo é igual do `RunInterval` conforme definido na configuração de conformidade de Chat persistente:</span><span class="sxs-lookup"><span data-stu-id="a74ca-139">This time interval is equal to the  `RunInterval` as set in the Persistent Chat Compliance configuration:</span></span>
  
```
void Translate(ConversationCollection conversations)
```

<span data-ttu-id="a74ca-140">O `ConversationCollection` contém as informações de conversação coletadas da última vez em que este método foi chamado.</span><span class="sxs-lookup"><span data-stu-id="a74ca-140">The  `ConversationCollection` contains the conversation information that was collected from the last time this method was called.</span></span>
  
## <a name="customize-the-xslt-definition-file"></a><span data-ttu-id="a74ca-141">Personalize o arquivo de definição do XSLT</span><span class="sxs-lookup"><span data-stu-id="a74ca-141">Customize the XSLT definition file</span></span>

<span data-ttu-id="a74ca-p110">Os dados de conformidade são entregues como XML, que você pode transformar no formato mais adequado para a sua organização usando um arquivo de definição XSLT. Este tópico descreve o arquivo XML que o serviço de Conformidade cria. Ele também fornece exemplos de arquivos de saída e definição XSLT.</span><span class="sxs-lookup"><span data-stu-id="a74ca-p110">The compliance data is delivered as XML, which you can transform into the format that best fits your organization, by using an XSLT definition file. This topic describes the XML file that the Compliance service creates. It also provides samples of XSLT definition and output files.</span></span>
  
### <a name="output-format"></a><span data-ttu-id="a74ca-145">Formato de saída</span><span class="sxs-lookup"><span data-stu-id="a74ca-145">Output format</span></span>

<span data-ttu-id="a74ca-146">A saída do serviço de Conformidade é categorizada por conversa (o elemento Conversation) e depois por mensagem (o elemento Messages), conforme mostrado no exemplo de código a seguir:</span><span class="sxs-lookup"><span data-stu-id="a74ca-146">The Compliance service output is categorized by conversation (the Conversation element) and then by message (the Messages element), as shown in the following code sample:</span></span>
  
```
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
```

<span data-ttu-id="a74ca-p111">Um elemento Conversation contém quatro elementos (Channel, FirstMessage, StartTimeUTC e EndTimeUTC). O elemento Channel contém o Uniform Resource Identifier (URI) da sala de chat, e o elemento FirstMessage descreve a primeira mensagem no elemento Messages. Os elementos StartTimeUTC e EndTimeUTC fornecem os horários de início e término da conversa, conforme mostrado no exemplo de código a seguir:</span><span class="sxs-lookup"><span data-stu-id="a74ca-p111">A Conversation element contains four elements (Channel, FirstMessage, StartTimeUTC, and EndTimeUTC). The Channel element contains the Uniform Resource Identifier (URI) of the chat room, and the FirstMessage element describes the first message in the Messages element. The StartTimeUTC and EndTimeUTC elements provide the start and end times for the conversation, as shown in the following code sample:</span></span>
  
```
<<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

<span data-ttu-id="a74ca-p112">Um elemento Message contém dois elementos (Sender e DateTimeUTC) e três atributos (Type, Content e ID). O elemento Sender representa o usuário que envia a mensagem e o elemento DateTimeUTC representa quando ocorre um evento, conforme mostrado no exemplo de código a seguir:</span><span class="sxs-lookup"><span data-stu-id="a74ca-p112">A Message element contains two elements (Sender and DateTimeUTC) and three attributes (Type, Content, and ID). The Sender element represents the user who sends the message, and the DateTimeUTC element represents when an event occurs, as shown in the following code sample:</span></span>
  
```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

<span data-ttu-id="a74ca-152">Os atributos de mensagem Type, Content e ID são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a74ca-152">The following table describes the message attributes Type, Content, and ID.</span></span>
  
<span data-ttu-id="a74ca-153">**Atributos do elemento Messages**</span><span class="sxs-lookup"><span data-stu-id="a74ca-153">**Messages Element Attributes**</span></span>

|<span data-ttu-id="a74ca-154">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="a74ca-154">**Attribute**</span></span>|<span data-ttu-id="a74ca-155">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a74ca-155">**Description**</span></span>|<span data-ttu-id="a74ca-156">**Opcional/necessários**</span><span class="sxs-lookup"><span data-stu-id="a74ca-156">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a74ca-157">Tipo</span><span class="sxs-lookup"><span data-stu-id="a74ca-157">Type</span></span>  <br/> |<span data-ttu-id="a74ca-p113">Especifica o tipo de mensagem. Os tipos de mensagens são descritos na tabela Tipos de mensagem dos elementos Messages.</span><span class="sxs-lookup"><span data-stu-id="a74ca-p113">Specifies the message type. The message types are described in the Message Elements Message Types table.</span></span>  <br/> |<span data-ttu-id="a74ca-160">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a74ca-160">Required</span></span>  <br/> |
|<span data-ttu-id="a74ca-161">Conteúdo</span><span class="sxs-lookup"><span data-stu-id="a74ca-161">Content</span></span>  <br/> |<span data-ttu-id="a74ca-p114">Contém o conteúdo da mensagem. As mensagens com um tipo Ingressar ou Participar não usam esse atributo.</span><span class="sxs-lookup"><span data-stu-id="a74ca-p114">Contains the content of the message. Messages with a Type of Join or Part do not use this attribute.</span></span>  <br/> |<span data-ttu-id="a74ca-164">Opcional</span><span class="sxs-lookup"><span data-stu-id="a74ca-164">Optional</span></span>  <br/> |
|<span data-ttu-id="a74ca-165">ID</span><span class="sxs-lookup"><span data-stu-id="a74ca-165">ID</span></span>  <br/> |<span data-ttu-id="a74ca-p115">Especifica a identificação exclusiva do conteúdo. Esse atributo é usado somente com mensagens com um tipo Chat.</span><span class="sxs-lookup"><span data-stu-id="a74ca-p115">Specifies the unique ID of the content. This attribute is used only with messages with a Type of Chat.</span></span>  <br/> |<span data-ttu-id="a74ca-168">Opcional</span><span class="sxs-lookup"><span data-stu-id="a74ca-168">Optional</span></span>  <br/> |
   
<span data-ttu-id="a74ca-p116">Cada elemento Sender contém cinco atributos: nome de usuário, identificação, email, interno e URI. Esses atributos são descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a74ca-p116">Each Sender element contains five attributes: the user name, ID, email, internal, and URI. These attributes are described in the following table.</span></span>
  
<span data-ttu-id="a74ca-171">**Atributos do elemento Sender**</span><span class="sxs-lookup"><span data-stu-id="a74ca-171">**Sender Element Attributes**</span></span>

|<span data-ttu-id="a74ca-172">**Atributo**</span><span class="sxs-lookup"><span data-stu-id="a74ca-172">**Attribute**</span></span>|<span data-ttu-id="a74ca-173">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a74ca-173">**Description**</span></span>|<span data-ttu-id="a74ca-174">**Opcional/necessários**</span><span class="sxs-lookup"><span data-stu-id="a74ca-174">**Optional/Required**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a74ca-175">Username</span><span class="sxs-lookup"><span data-stu-id="a74ca-175">Username</span></span>  <br/> |<span data-ttu-id="a74ca-176">O nome do remetente.</span><span class="sxs-lookup"><span data-stu-id="a74ca-176">The name of the sender.</span></span>  <br/> |<span data-ttu-id="a74ca-177">Opcional</span><span class="sxs-lookup"><span data-stu-id="a74ca-177">Optional</span></span>  <br/> |
|<span data-ttu-id="a74ca-178">ID</span><span class="sxs-lookup"><span data-stu-id="a74ca-178">ID</span></span>  <br/> |<span data-ttu-id="a74ca-179">ID exclusiva de. do remetente</span><span class="sxs-lookup"><span data-stu-id="a74ca-179">The sender's unique ID.</span></span>  <br/> |<span data-ttu-id="a74ca-180">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a74ca-180">Required</span></span>  <br/> |
|<span data-ttu-id="a74ca-181">Email</span><span class="sxs-lookup"><span data-stu-id="a74ca-181">Email</span></span>  <br/> |<span data-ttu-id="a74ca-182">Endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="a74ca-182">The sender's email address.</span></span>  <br/> |<span data-ttu-id="a74ca-183">Opcional</span><span class="sxs-lookup"><span data-stu-id="a74ca-183">Optional</span></span>  <br/> |
|<span data-ttu-id="a74ca-184">Interno</span><span class="sxs-lookup"><span data-stu-id="a74ca-184">Internal</span></span>  <br/> |<span data-ttu-id="a74ca-p117">Determina se o usuário é um usuário interno ou um usuário federado. Se o valor for definido como true, o usuário será interno.</span><span class="sxs-lookup"><span data-stu-id="a74ca-p117">Determines whether the user is an internal user or a federated user. If the value is set to true, the user is internal.</span></span>  <br/> |<span data-ttu-id="a74ca-187">Opcional</span><span class="sxs-lookup"><span data-stu-id="a74ca-187">Optional</span></span>  <br/> |
|<span data-ttu-id="a74ca-188">Uri</span><span class="sxs-lookup"><span data-stu-id="a74ca-188">Uri</span></span>  <br/> |<span data-ttu-id="a74ca-189">URI do SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="a74ca-189">The user's SIP URI.</span></span>  <br/> |<span data-ttu-id="a74ca-190">Obrigatório</span><span class="sxs-lookup"><span data-stu-id="a74ca-190">Required</span></span>  <br/> |
   
<span data-ttu-id="a74ca-191">Os exemplos a seguir mostram os tipos de mensagem que o elemento Messages pode conter.</span><span class="sxs-lookup"><span data-stu-id="a74ca-191">The following examples show the message types that the Messages element can contain.</span></span> <span data-ttu-id="a74ca-192">Ela também fornece exemplos de como cada elemento é usado.</span><span class="sxs-lookup"><span data-stu-id="a74ca-192">It also provides examples of how each element is used.</span></span>
  
<span data-ttu-id="a74ca-193">JOIN - um usuário ingressa em uma sala de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="a74ca-193">Join - A user joins a chat room.</span></span>
  
```
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

<span data-ttu-id="a74ca-194">Parte - um usuário sai de uma sala de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="a74ca-194">Part - A user leaves a chat room.</span></span>
  
```
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

<span data-ttu-id="a74ca-195">Bate-papo - endereço de email do remetente.</span><span class="sxs-lookup"><span data-stu-id="a74ca-195">Chat - The sender's email address.</span></span>
  
```
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

<span data-ttu-id="a74ca-196">Chat persistente - um usuário solicita o conteúdo do histórico de chat.</span><span class="sxs-lookup"><span data-stu-id="a74ca-196">Backchat - A user requests content from chat history.</span></span>
  
```
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

<span data-ttu-id="a74ca-197">Upload de arquivo - um usuário carrega um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a74ca-197">File upload - A user uploads a file.</span></span>
  
```
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

<span data-ttu-id="a74ca-198">Download de arquivo - um usuário baixa um arquivo.</span><span class="sxs-lookup"><span data-stu-id="a74ca-198">File download - A user downloads a file.</span></span>
  
```
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a><span data-ttu-id="a74ca-199">XSD de saída de Chat persistente padrão e exemplo de transformação em XSL</span><span class="sxs-lookup"><span data-stu-id="a74ca-199">Default Persistent Chat Output XSD and Example XSL Transform</span></span>

<span data-ttu-id="a74ca-200">O exemplo de código a seguir contém a saída padrão do Servidor de Conformidade:</span><span class="sxs-lookup"><span data-stu-id="a74ca-200">The following code sample contains the default output from the Compliance Server:</span></span>
  
```
<?xml version="1.0" encoding="utf-8"?>
<xs:schema id="Conversations" xmlns="" xmlns:xs="http://www.w3.org/2001/XMLSchema" xmlns:msdata="urn:schemas-microsoft-com:xml-msdata">
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
```

<span data-ttu-id="a74ca-201">O exemplo de código a seguir contém um exemplo de transformação em XSL:</span><span class="sxs-lookup"><span data-stu-id="a74ca-201">The following code sample contains a sample XSL transform:</span></span>
  
```
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

```