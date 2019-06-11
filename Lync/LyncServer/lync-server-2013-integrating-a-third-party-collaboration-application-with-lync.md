---
title: Integrando um aplicativo de colaboração de terceiros com o Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b56fabbc1bd341e3ba2c5fe535d147c09335b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Integrando um aplicativo de colaboração de terceiros com o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-20_

Você pode integrar o Lync 2013 com qualquer aplicativo de colaboração online de terceiros adicionando informações sobre o aplicativo ao registro. Você pode usar o Lync 2013 para iniciar sessões de conferência de dados hospedadas em um servidor interno, um serviço baseado na Internet ou ambos. A sessão de colaboração ou de data conferência pode ser iniciada a partir da lista de contatos ou de uma sessão de mensagens instantâneas, voz ou vídeo existente. O Lync 2013 funciona apenas como veículo para iniciar o aplicativo. Qualquer conversa existente do Lync 2013 permanecerá ativa após o início da sessão de colaboração online.

As seções a seguir descrevem como integrar o Lync 2013 com aplicativos de colaboração baseados em servidor e baseados na Internet.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Integrando um aplicativo de colaboração baseado na Internet com o Lync 2013

Geralmente, as etapas envolvidas na integração de um aplicativo de colaboração de terceiros são as seguintes:

1.  Informações sobre o aplicativo são adicionadas ao registro.

2.  O organizador entra no Lync 2013 e seleciona contatos para compartilhamento de dados e colaboração. Ou o organizador pode já estar em uma conversa e decidir adicionar a conferência de dados.

3.  O Lync 2013 lê o registro, inicia o aplicativo de colaboração e, em seguida, envia uma mensagem SIP personalizada — um appINVITE — para os participantes selecionados.

4.  Os participantes aceitam o convite e o aplicativo de colaboração é iniciado no computador de cada pessoa. O Lync 2013 usa o registro para determinar qual aplicativo de colaboração usar e, em seguida, inicia esse aplicativo usando os parâmetros incluídos na mensagem appINVITE.

A tabela a seguir descreve as entradas do Registro necessárias para integrar um aplicativo de colaboração baseado na Internet com o Lync 2013. Essas entradas são colocadas no registro no seguinte local:

  - HKEY\_local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\aplicativos\\parâmetros

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Entradas do registro para um aplicativo de colaboração baseado na Internet

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Dados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome</p></td>
<td><p>REG_SZ</p></td>
<td><p>O nome do aplicativo para os menus do Lync 2013.</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>Caminho para o ícone de 16 pixels x 16 pixels, BMP ou PNG.</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Caminho do participante para iniciar o aplicativo de colaboração online.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Caminho do organizador para iniciar o aplicativo de colaboração online. Esse caminho pode conter um ou mais parâmetros personalizados, conforme definido na subchave Parameters. Por exemplo,<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DUPLA</p></td>
<td><p>0 = sessão local. O aplicativo é iniciado no computador local.</p>
<p>1 = sessão de dois participantes (padrão). O Lync 2013 inicia o aplicativo localmente e, em seguida, envia uma notificação do sistema para o outro usuário. O outro usuário clica na notificação e inicia o aplicativo especificado em seu computador.</p>
<p>2 = sessão com vários participantes. O Lync 2013 inicia o aplicativo localmente e, em seguida, envia notificações do sistema para os outros usuários, solicitando que eles iniciem o aplicativo especificado em seu próprio computador.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Uma lista dos menus em que esse comando será exibido, separados por ponto-e-vírgula. Os valores possíveis são:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Se ExtensibleMenu não for definido, os valores padrão de MainWindowRightClick e ConversationWindowActions serão usados.</p></td>
</tr>
</tbody>
</table>


A tabela a seguir descreve as entradas do registro para parâmetros. Essas entradas são locais em HKEY\_software\_\\\\User atual Microsoft\\Office\\15,0\\Lync\\SessionManager\\apps\\Parameters.

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Entradas do registro para um aplicativo de colaboração baseado na Internet

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Dados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>Usado em formato de token (<code>%Parm1%</code>) para adicionar valores específicos do usuário para a chave do Registro OriginatorPath.</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
<td><p>REG_SZ</p></td>
<td><p>Consulte param1.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Consulte param1.</p></td>
</tr>
</tbody>
</table>


As configurações de registro de exemplo a seguir integram o cliente de colaboração do ADatum com o Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>Integrando um aplicativo de colaboração baseado em servidor com o Lync 2013

As configurações para adicionar comandos para iniciar um aplicativo de colaboração baseado em servidor no Lync 2013 são semelhantes às descritas na seção anterior, integrando um aplicativo de colaboração baseado na Internet com o Lync 2013. No entanto, o OriginatorPath não é necessário e alguns valores são alterados. As entradas do registro são colocadas no seguinte local:

  - HKEY\_local\_MACHINE\\software\\Microsoft\\Office\\15,0\\Lync\\SessionManager\\aplicativos\\parâmetros

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>Entradas do registro para um aplicativo de colaboração baseado em servidor

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Tipo</th>
<th>Dados</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome</p></td>
<td><p>REG_SZ</p></td>
<td><p>Nome do aplicativo exibido no menu.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>DUPLA</p></td>
<td><p>Valor = 1. Define o tipo de aplicativo como protocolo. Os outros valores possíveis não se aplicam nesse caso. Se não estiver presente, ApplicationType será definido como 0 (executável).</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Protocolo usado para iniciar o aplicativo de colaboração. Para o Live Meeting 2007, o valor de Path é definido <code>meet:%conf-uri%</code>como.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DUPLA</p></td>
<td><p>0 = sessão local. O aplicativo é iniciado no computador local.</p>
<p>1 = sessão de dois participantes (padrão). O Lync 2013 inicia o aplicativo localmente e, em seguida, envia uma notificação do sistema para o outro usuário. O outro usuário clica na notificação e inicia o aplicativo especificado em seu computador.</p>
<p>2 = sessão com vários participantes. O Lync 2013 inicia o aplicativo localmente e, em seguida, envia notificações do sistema para os outros usuários, solicitando que eles iniciem o aplicativo especificado em seu computador.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = o tipo de servidor.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Uma lista dos menus em que esse comando será exibido, separados por ponto-e-vírgula. Os valores possíveis são:</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Se ExtensibleMenu não for definido, os valores padrão de MainWindowRightClick e ConversationWindowActions serão usados.</p></td>
</tr>
</tbody>
</table>


O exemplo a seguir adiciona comandos para iniciar o ADatum de colaboração do cliente no Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

