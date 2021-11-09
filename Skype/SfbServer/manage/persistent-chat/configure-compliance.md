---
title: Configurar o serviço de Conformidade para o Servidor de Chat Persistente no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 24e36ea3-fb8a-45a4-b6b7-38c2e256b218
description: 'Resumo: saiba como configurar o serviço de Conformidade do Servidor de Chat Persistente Skype for Business Server 2015.'
ms.openlocfilehash: 23f28c2071063e2729deb54eea9703a7699e3e07
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60858238"
---
# <a name="configure-the-compliance-service-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Configurar o serviço de Conformidade para o Servidor de Chat Persistente no Skype for Business Server 2015

**Resumo:** Saiba como configurar o serviço de Conformidade do Servidor de Chat Persistente Skype for Business Server 2015.

A conformidade com o Chat Persistente permite que os administradores mantenham um arquivo morto de mensagens de Chat Persistente, bem como atividades. O serviço de Conformidade registra e arquiva dados relacionados a cada conversa do Servidor de Chat Persistente, incluindo quando um participante:

- Insinte uma sala de Chat Persistente

- Sai de uma sala de chat

- Posta uma mensagem

- Exibe o histórico do chat

- Carrega um arquivo

- Baixa um arquivo

Essas informações podem ser recuperadas do banco de dados De conformidade SQL conforme necessário. 

> [!NOTE]
> O chat persistente está disponível no Skype for Business Server 2015, mas não tem mais suporte no Skype for Business Server 2019. A mesma funcionalidade está disponível no Teams. Para obter mais informações, consulte [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here). Se você precisar usar o chat persistente, suas opções são migrar usuários que exigem essa funcionalidade para Teams ou continuar usando o Skype for Business Server 2015. 

## <a name="configure-the-compliance-service-by-using-windows-powershell"></a>Configurar o serviço de Conformidade usando Windows PowerShell

Depois que o serviço de Conformidade tiver sido habilitado usando o Construtor de Topologias, você poderá configurar o serviço usando o cmdlet **Set-CsPersistenChatComplianceConfiguration:**

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Identity <XdsIdentity>] <COMMON PARAMETERS>
```

ou

```PowerShell
Set-CsPersistentChatComplianceConfiguration [-Instance <PSObject>] <COMMON PARAMETERS>
```

Você pode definir os seguintes parâmetros:

- AdapterType - Permite especificar o tipo de adaptador. Um adaptador é um produto de terceiros que converte os dados no banco de dados de conformidade em um formato específico. XML é o padrão.

- OneChatRoomPerOutputFile - Esse parâmetro permite que você especifique os relatórios separados a serem criados para cada sala de chat.

- AddChatRoomDetails - Quando habilitado, esse parâmetro registra detalhes adicionais sobre cada sala de chat no banco de dados. Como essa configuração pode aumentar muito o tamanho do banco de dados, ela é desabilitada por padrão.

- AddUserDetails - Quando habilitado, esse parâmetro registra detalhes adicionais sobre cada usuário da sala de chat no banco de dados. Como essa configuração pode aumentar muito o tamanho do banco de dados, ela é desabilitada por padrão.

- Identidade - Esse parâmetro permite que as configurações de conformidade sejam escopos para um conjunto específico, incluindo os níveis global, de site e de serviço. O padrão é o nível global. 

- RunInterval - Esse parâmetro dita o tempo antes de o servidor criar o próximo arquivo de saída de conformidade (o padrão é 15 minutos).

## <a name="use-a-customized-compliance-adapter"></a>Usar um adaptador de conformidade personalizado

Você pode escrever um adaptador personalizado em vez de usar o XmlAdapter instalado com o Servidor de Chat Persistente. Para realizar isso, você deve oferecer um assembly .NET Framework que contém uma classe pública que implementa a interface do **IComplianceAdapter**. Você deve colocar esse assembly na pasta de instalação do Servidor de Chat Persistente de cada servidor no pool do Servidor de Chat Persistente. Qualquer um dos servidores de Conformidade podem oferecer dados de conformidade para seu adaptador, mas os servidores de conformidade não oferecerão dados de conformidade duplicados para várias instâncias do seu adaptador.

A interface é definida no assembly Compliance.dll no namespace  `Microsoft.Rtc.Internal.Chat.Server.Compliance` . A interface define dois métodos que seu adaptador personalizado deve implementar.

O servidor de Conformidade de Chat Persistente chamará o método a seguir quando o adaptador for carregado pela primeira vez. A  `AdapterConfig` contém a configuração de conformidade de Chat Persistente que é relevante para o adaptador de conformidade:

```cpp
void SetConfig(AdapterConfig config)
```

O servidor de Conformidade de Chat Persistente chama o seguinte método em intervalos periódicos, desde que haja novos dados a ser traduzidos. Esse intervalo de tempo é igual ao definido na configuração de  `RunInterval` Conformidade de Chat Persistente:

```cpp
void Translate(ConversationCollection conversations)
```

O  `ConversationCollection` contém as informações de conversa que foram coletadas da última vez que esse método foi chamado.

## <a name="customize-the-xslt-definition-file"></a>Personalizar o arquivo de definição XSLT

Os dados de conformidade são entregues como XML, que você pode transformar no formato que melhor se ajusta à sua organização, usando um arquivo de definição XSLT. Este tópico descreve o arquivo XML que o serviço de Conformidade cria. Ele também fornece exemplos de arquivos de saída e definição XSLT.

### <a name="output-format"></a>Formato de saída

A saída do serviço de Conformidade é categorizada por conversa (o elemento Conversation) e, em seguida, por mensagem (o elemento Messages), conforme mostrado no exemplo de código a seguir:

```XML
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

Um elemento Conversation contém quatro elementos (Channel, FirstMessage, StartTimeUTC e EndTimeUTC). O elemento Channel contém o URI (Uniform Resource Identifier) da sala de chat, e o elemento FirstMessage descreve a primeira mensagem no elemento Messages. Os elementos StartTimeUTC e EndTimeUTC fornecem os horários de início e término da conversa, conforme mostrado no exemplo de código a seguir:

```xml
<FirstMessage type="JOIN" content="" id="0">
      <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
      <DateTimeUTC since1970="1212610540953" string="2008-06-04T20:15:40.9535482Z" long="633482073409535482" /> 
</FirstMessage>
```

Um elemento Message contém dois elementos (Sender e DateTimeUTC) e três atributos (Type, Content e ID). O elemento Sender representa o usuário que envia a mensagem e o elemento DateTimeUTC representa quando ocorre um evento, conforme mostrado no exemplo de código a seguir:

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message>
```

Os atributos de mensagem Type, Content e ID são descritos na tabela a seguir.

**Atributos do elemento Messages**

|**Atributo**|**Descrição**|**Opcional/Obrigatório**|
|:-----|:-----|:-----|
|Tipo  <br/> |Especifica o tipo de mensagem. Os tipos de mensagens são descritos na tabela Tipos de mensagem dos elementos Messages.  <br/> |Obrigatório  <br/> |
|Conteúdo  <br/> |Contém o conteúdo da mensagem. As mensagens com um tipo Ingressar ou Participar não usam esse atributo.  <br/> |Opcional  <br/> |
|ID  <br/> |Especifica a identificação exclusiva do conteúdo. Esse atributo é usado somente com mensagens com um tipo Chat.  <br/> |Opcional  <br/> |

Cada elemento Sender contém cinco atributos: nome de usuário, identificação, email, interno e URI. Esses atributos são descritos na tabela a seguir.

**Atributos do elemento Sender**

|**Atributo**|**Descrição**|**Opcional/Obrigatório**|
|:-----|:-----|:-----|
|Nome de usuário  <br/> |O nome do remetente.  <br/> |Opcional  <br/> |
|ID  <br/> |A ID exclusiva do remetente.  <br/> |Obrigatório  <br/> |
|Email  <br/> |O endereço de email do remetente.  <br/> |Opcional  <br/> |
|Interno  <br/> |Determina se o usuário é um usuário interno ou um usuário federado. Se o valor for definido como true, o usuário será interno.  <br/> |Opcional  <br/> |
|Uri  <br/> |URI SIP do usuário.  <br/> |Obrigatório  <br/> |

Os exemplos a seguir mostram os tipos de mensagem que o elemento Messages pode conter. Ela também fornece exemplos de como cada elemento é usado.

Ingressar - Um usuário ins junta uma sala de chat.

```xml
<Message type="JOIN" content="" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206211842612" string="2008-03-22T18:50:42.6127374Z" long="633418086426127374" /> 
</Message
```

Parte - Um usuário sai de uma sala de chat.

```xml
<Message type="PART" content="" id="0">
  < Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212610602532" string="2008-06-04T20:16:42.5324614Z" long="633482074025324614" /> 
</Message>
```

Chat - O endereço de email do remetente.

```xml
<Message type="CHAT" content="hello" id="1">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351800522" string="2008-03-12T19:56:40.522264Z" long="633409486005222640" /> 
</Message>
```

Backchat - Um usuário solicita conteúdo do histórico de chat.

```xml
<Message type="BACKCHAT" content="backchatcontent" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1206034385284" string="2008-03-20T17:33:05.2841594Z" long="633416311852841594" /> 
</Message>
```

Carregamento de arquivo - Um usuário carrega um arquivo.

```xml
<Message type="FILEUPLOAD" content="0988239a-bb66-4616-90a4-b07771a2097c.txt" id="0">
  <Sender UserName="TestUser kazuto" id="10" email="kazuto@litwareinc.com" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1205351828975" string="2008-03-12T19:57:08.9755711Z" long="633409486289755711" /> 
</Message>
```

Download de arquivo - Um usuário baixa um arquivo.

```xml
<Message type="FILEDOWNLOAD" content="006074ca-24f0-4b35-8bd8-98006a2d1aa8.txt" id="0">
  <Sender UserName="kazuto@litwareinc.com" id="10" email="" internal="true" uri="kazuto@litwareinc.com" /> 
  <DateTimeUTC since1970="1212611141851" string="2008-06-04T20:25:41.8518646Z" long="633482079418518646" /> 
</Message>
```

### <a name="default-persistent-chat-output-xsd-and-example-xsl-transform"></a>XSD de saída de chat persistente padrão e Exemplo XSL Transform

O exemplo de código a seguir contém a saída padrão do Servidor de Conformidade:

```xml
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

O exemplo de código a seguir contém uma transformação XSL de exemplo:

```xml
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
