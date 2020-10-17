---
title: 'Lync Server 2013: preparando o esquema do Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27c785596d1fe994e3156eb0e52ed840609a5c26
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506848"
---
# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>Preparando o esquema do Active Directory no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-08-27_

Antes de começar a preparar os serviços de domínio do Active Directory, você pode abrir os arquivos de esquema usando um editor de texto, como o bloco de notas do Windows, ou ver [extensões, classes e atributos de esquema do Active Directory usados pelo Lync server 2013](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md) para examinar todas as extensões de esquema de serviços de domínio do Active Directory que serão modificadas para o lync Server 2013. O Lync Server usa quatro arquivos de esquema:

  - ExternalSchema. ldf, que é usado para interoperabilidade com o Microsoft Exchange Server

  - ServerSchema. ldf, que é o arquivo de esquema principal do Lync Server 2013

  - BackCompatSchema.ldf, que é usado para a interoperabilidade com quaisquer componentes de versões anteriores

  - VersionSchema.ldf, que é usado para informações sobre a versão do esquema preparado

Todos os arquivos .ldf são instalados durante a preparação do esquema, sem levar em conta se é uma migração de uma versão anterior ou se é uma instalação limpa. Esses arquivos de esquema são instalados na sequência mostrada na lista anterior e estão localizados na \\ pasta de esquema de suporte \\ na mídia de instalação.

As extensões de esquema do Lync Server são replicadas em todos os domínios, o que impacta o tráfego de rede. Execute a preparação do esquema quando a utilização da rede estiver baixa.

<div>


> [!NOTE]  
> Se você precisar adicionar suporte para o Microsoft® Office Communicator Mobile 2007 R2 para Java e o Microsoft® Office Communicator Mobile para clientes móveis da Nokia 1,0 à sua implantação do Lync Server 2013, será necessário preparar o esquema do Active Directory para o Microsoft Office Communications Server 2007 R2 durante a instalação do Lync Server 2013. Para obter o software e a documentação necessários, consulte <A href="https://go.microsoft.com/fwlink/p/?linkid=207172">https://go.microsoft.com/fwlink/p/?linkId=207172</A> .



</div>

<div>

## <a name="adsi-edit"></a>Editor ADSI

Active Directory Service Interfaces Editor (Editor ADSI) é uma ferramenta de administração AD DS que você pode usar para verificar a preparação e a replicação de esquema.

O Editor ADSI é instalado por padrão quando você instala a função AD DS para transformar um servidor em um controlador de domínio. Para o Windows Server 2008 e o Windows Server 2008 R2, o ADSI Edit (Adsiedit. msc) está incluído nas ferramentas de administração de servidor remoto (RSAT). Você também pode instalar o RSAT em servidores de membro de domínio ou servidores autônomos. O pacote RSAT é copiado a esses servidores por padrão quando o Windows é instalado, mas não é instalado por padrão. Instale as ferramentas individuais usando o Gerenciador de Servidores. O ADSI Edit está incluído em **Ferramentas de Administração de Funções**, **Ferramentas de Serviços de Domínio Active Directory**, **Ferramentas do Controlador de Domínio do Active Directory**.

Para o Windows Server 2003, o ADSI Edit está incluído nas Ferramentas de Suporte. As ferramentas de suporte estão disponíveis no CD do Windows Server 2003 na \\ \\ pasta ferramentas de suporte ou você pode baixá-las de "ferramentas de suporte do windows Server 2003 Service Pack 2 32-bit" em [https://go.microsoft.com/fwlink/p/?linkId=125770](https://go.microsoft.com/fwlink/p/?linkid=125770) . As instruções para instalar as ferramentas de suporte do CD do produto estão disponíveis em "instalar ferramentas de suporte do Windows" em [https://go.microsoft.com/fwlink/p/?linkId=125771](https://go.microsoft.com/fwlink/p/?linkid=125771) . O arquivo Adsiedit.dll é automaticamente registrado quando você instala as ferramentas de suporte. Se, no entanto, você tiver copiado os arquivos para o computador, deverá executar o comando **regsvr32** para registrar o arquivo adsiedit.dll e executar a ferramenta.

</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Executando a preparação do esquema do Active Directory no Lync Server 2013](lync-server-2013-running-schema-preparation.md)

  - [Verificando a replicação do esquema do Active Directory no Lync Server 2013](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Preparando a floresta para o Lync Server 2013](lync-server-2013-preparing-the-forest.md)  
[Preparando domínios para o Lync Server 2013](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

