---
title: 'Lync Server 2013: usando a ferramenta de personalização do Office (OCT)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using the Office Customization Tool (OCT)
ms:assetid: 26647cb6-ba84-4ba7-8b6f-2cf86818e530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204748(v=OCS.15)
ms:contentKeyID: 48183654
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2203c4169075b7b906156bf3436e61011f873a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007470"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Usando a ferramenta de personalização do Office (OCT) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-02_

A OCT (ferramenta de personalização do Office) faz parte do programa de instalação e é a ferramenta recomendada para várias personalizações. Usando a OCT, você personaliza o Office e salva suas personalizações em um arquivo de personalização de instalação. msp. Coloque o arquivo na pasta Atualizações no ponto de instalação na rede. Quando você instala o Office, a instalação procura um arquivo de personalização da instalação na pasta Atualizações e aplica as personalizações. A pasta Atualizações pode ser usada apenas para implantar atualizações de software durante uma instalação inicial do Office 2013.

A OCT é parte da configuração e está incluída nas versões de licença de volume do produto. Você executa a OCT digitando `setup.exe /admin` na linha de comando a partir da raiz do ponto de instalação de rede que contém os arquivos de origem do Office 2013. Por exemplo, use o seguinte:

`\\server\share\Office15\setup.exe /admin`

Os administradores usam a OCT para criar um arquivo de personalização de instalação. msp. Como no Microsoft Office 2010 OCT, os administradores podem personalizar as seguintes áreas:

  - **Configuração** Usado para especificar o local de instalação padrão no cliente e o nome da organização padrão, fontes de instalação de rede adicionais, chave de produto, contrato de licença de usuário final, nível de exibição, versões anteriores do Office para remover, programas personalizados para executar durante a instalação, configurações de segurança e propriedades de instalação.

  - **Recursos** do Usado para definir as configurações do usuário e para personalizar como os recursos do Office são instalados. Os administradores podem usar a OCT para especificar os valores padrão iniciais das configurações de aplicativo do Office para os usuários. Os usuários podem modificar a maioria das configurações após a instalação.

  - **Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do registro e configurar atalhos.

  - **Outlook** Usado para personalizar o perfil padrão do Outlook do usuário, especificar as configurações do Exchange, adicionar contas, remover contas e exportar configurações e\\especificar grupos de recebimento de envio.

Para obter informações sobre a OCT, <http://go.microsoft.com/fwlink/p/?linkid=267516>consulte.

</div>

<span> </span>

</div>

</div>

</div>

