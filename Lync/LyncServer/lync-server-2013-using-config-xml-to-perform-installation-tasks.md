---
title: 'Lync Server 2013: usando o config. xml para executar tarefas de instalação'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2933da3fc52cc6a5c23f74806ff3a4e81dcb2ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212827"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>Usando o config. xml para executar tarefas de instalação no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

Embora a Ferramenta de Personalização do Office (OCT) seja a ferramenta principal para instalação com personalização, os administradores podem usar o arquivo Config.xml para especificar instruções de instalação adicionais que não estão disponíveis na OCT. As personalizações a seguir só podem ser feitas usando o arquivo Config.xml:

  - Especificar o caminho do ponto de instalação de rede.

  - Selecionar os produtos a serem instalados.

  - Configure o registro em log e o local do arquivo de personalização da Instalação e atualizações de software.

  - Especifique as opções de instalação, como nome do usuário.

  - Copiar a LIS (origem de instalação local) no computador do usuário, mas sem instalar o Office.

  - Adicionar ou remover idiomas da instalação.

Recomendamos que você use o arquivo config. xml para configurar a instalação silenciosa do Lync 2013.

Por padrão, o arquivo config. xml armazenado na pasta principal do produto (por exemplo, \\produto. WW) direciona a instalação para instalar o produto. Por exemplo, o arquivo config. xml na pasta a seguir instala o Lync 2013:

  - \\\\Server\\share\\Lync15\\Lync. WW \\config. xml

Os elementos config. XML usados com mais frequência para a instalação do Lync 2013 estão listados na tabela a seguir.

### <a name="configxml-elements"></a>Elementos de Config.xml

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Configuração</p></td>
<td><p>Elemento de nível superior (obrigatório). Contém o atributo Product, por exemplo: Product=Lync</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>Especifica como os recusos de produto específicos são manipulados durante a instalação. Use os seguintes atributos para impedir a instalação dos serviços corporativos de conectividade, que incluem componentes compartilhados que interferem no Outlook 2010:</p>
<ul>
<li><p>ID =&quot;LOBiMain&quot;</p></li>
<li><p>Estado =&quot;ausente&quot;</p></li>
<li><p>Children =&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Exibir</p></td>
<td><p>O nível deUI que a Instalação exibe para o usuário. Entre os atributos comuns estão os seguintes:</p>
<ul>
<li><p>CompletionNotice =&quot;sim&quot; | &quot;não&quot;(padrão)</p></li>
<li><p>AcceptEula =&quot;sim&quot; | &quot;não&quot;(padrão)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Registro em log</p></td>
<td><p>Opções para o tipo de registro em log executado pela Instalação. Entre os atributos comuns estão os seguintes:</p>
<ul>
<li><p>Digite =&quot;off&quot; | &quot;Standard&quot;(padrão) | &quot;Detalhado&quot;</p></li>
<li><p>Template=”filename.txt” (o nome do arquivo de log)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Configuração</p></td>
<td><p>Especifica valores para as propriedades do Windows Installer. Entre os atributos comuns estão os seguintes:</p>
<ul>
<li><p>ID da configuração&quot;=&quot; nome (o nome da Propriedade do Windows Installer)</p></li>
<li><p>Valor =&quot;valor&quot; (o valor a ser atribuído à propriedade)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>O caminho totalmente qualificado do ponto de instalação de rede do qual a instalação deve ser executada. Inclui o atributo Location:</p>
<ul>
<li><p>Location = "caminho"</p></li>
</ul></td>
</tr>
</tbody>
</table>


O exemplo a seguir mostra um arquivo config. xml para uma instalação silenciosa típica do Lync 2013.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Informações detalhadas sobre como usar o arquivo config. xml para executar tarefas de instalação e manutenção do Office <https://go.microsoft.com/fwlink/p/?linkid=267514>estão disponíveis em.

<div>

## <a name="to-customize-the-configxml-file"></a>Para personalizar o arquivo Config.xml

1.  Abra o arquivo Config.xml usando uma ferramenta editora de texto, como o Bloco de Notas.

2.  Localize as linhas que contêm os elementos que você deseja alterar.

3.  Modifique a entrada do elemento com as opções silenciosas que você deseja usar. Certifique-se de remover os delimitadores de comentário,\<\!"--" e "-\>-". Por exemplo, use a seguinte sintaxe:
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Salve o arquivo Config.xml.

</div>

</div>

<span> </span>

</div>

</div>

</div>

