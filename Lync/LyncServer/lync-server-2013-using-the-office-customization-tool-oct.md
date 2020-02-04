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
ms.openlocfilehash: b82db655a0b55858de9cdc32efd1a3f110247b54
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743841"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-office-customization-tool-oct-in-lync-server-2013"></a>Usar a ferramenta de personalização do Office (OCT) no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-02_

O Office Customization Tool (OCT) faz parte do programa de Instalação e é a ferramenta recomendada para várias personalizações. Ao usar o OCT, você personaliza o Office e salva suas personalizações em um arquivo msp de personalização de Instalação. Você coloca o arquivo na pasta Atualizações no ponto de instalação de rede. Ao instalar o Office, a Instalação procura por um arquivo de personalização da Instalação na pasta Atualizações e aplica as personalizações. A pasta Atualizações pode ser usada somente para implantar atualizações de software durante uma instalação inicial do Office 2013.

O OCT faz parte da instalação e está incluído em versões de licença de volume do produto. Você executa a OCT digitando `setup.exe /admin` na linha de comando da raiz do ponto de instalação da rede que contém os arquivos de origem do Office 2013. Por exemplo, use o seguinte:

`\\server\share\Office15\setup.exe /admin`

Os administradores usam o OCT para criar um arquivo .msp de personalização da instalação. Como no Microsoft Office 2010 OCT, os administradores podem personalizar as seguintes áreas:

  - **Configurar** Usado para especificar o local de instalação padrão no cliente e o nome da organização padrão, origens adicionais de instalação de rede, chave do produto, contrato de licença de usuário final, nível de exibição, versões anteriores do Office para remover, programas personalizados para executar durante a instalação, configurações de segurança e propriedades de configuração.

  - **Recursos** do Usado para definir as configurações do usuário e para personalizar como os recursos do Office são instalados. Os administradores podem usar o OCT para especificar os valores padrões iniciais das configurações do aplicativo do Office para usuários. Os usuários podem modificar a maioria das configurações após a instalação.

  - **Conteúdo adicional** Usado para adicionar ou remover arquivos, adicionar ou remover entradas do registro e configurar atalhos.

  - **Outlook** Usado para personalizar o perfil padrão do Outlook de um usuário, especifique as configurações do Exchange, adicione contas, Remova contas e exporte\\configurações e especifique os grupos de recebimento de envio.

Para obter informações sobre a OCT, <http://go.microsoft.com/fwlink/p/?linkid=267516>consulte.

</div>

<span> </span>

</div>

</div>

</div>

