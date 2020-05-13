---
title: 'Lync Server 2013: visão geral do ambiente híbrido do Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Lync Server 2013 hybrid environment
ms:assetid: 0d16ec3a-28f0-4483-96e7-8e68f30398fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204669(v=OCS.15)
ms:contentKeyID: 48183399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e3fe59038c022dafcf7eeedb0079ae1a8cc63fd1
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-the-lync-server-2013-hybrid-environment"></a>Visão geral do ambiente híbrido do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-28_

O ambiente híbrido do Lync Server 2013 refere-se a uma implantação na qual há alguns usuários hospedados no Lync Server local 2013 e outros usuários hospedados no Lync Online, mas os usuários compartilham o mesmo domínio, como user@contoso.com.

<div>

## <a name="about-this-guide"></a>Sobre este guia

Este guia descreve as tarefas necessárias para configurar seu ambiente do Lync Server 2013 para interoperabilidade com o Lync Online e, em seguida, para mover os usuários da sua implantação local para usar o Lync Online.

</div>

<div>

## <a name="prerequisites"></a>Pré-requisitos

Você precisará ter os seguintes aplicativos e utilitários instalados para concluir as tarefas de configuração de uma implantação para o híbrido. Os instaladores desses arquivos estão incluídos na mídia de instalação fornecida para sua implantação, bem como nos links incluídos na lista a seguir.

  - [Serviços de Federação do Active Directory (AD FS) 2.0](https://go.microsoft.com/fwlink/p/?linkid=257305)

  - [Ferramenta de sincronização de diretórios da Microsoft 9,1](https://go.microsoft.com/fwlink/p/?linkid=257307)

  - [Instalar o Windows PowerShell para logon único com o AD FS](https://go.microsoft.com/fwlink/p/?linkid=398710)

  - O assistente de conexão do Microsoft Online Services (msoidcli-7.0. msi) está incluído na configuração da área de trabalho do Microsoft 365, que pode ser obtida da página de downloads vinculada a partir do centro de administração do Microsoft 365.

</div>

<div>

## <a name="administrator-credentials"></a>Credenciais de administrador

Quando você for solicitado a fornecer as credenciais de administrador, use o nome de usuário e a senha da conta de administrador da sua organização do Microsoft 365 ou do Office 365. Você também usará essas credenciais ao configurar o AD FS (serviços de Federação do Active Directory) 2,0, sincronização de diretórios, logon único, Federação e transferência de usuários para o Lync Online.

</div>

<div>

## <a name="connecting-to-lync-online-powershell"></a>Conectando-se ao PowerShell do Lync Online

Agora, os administradores têm a capacidade de usar o Windows PowerShell para gerenciar o Lync Online e suas contas de usuário do Lync Online. Para fazer isso, primeiro você deve baixar e instalar o módulo do conector do Lync Online no centro de download da Microsoft ( https://go.microsoft.com/fwlink/?LinkId=294688) . Para obter mais informações sobre como baixar, instalar e usar o módulo do conector do Lync Online e para obter informações detalhadas sobre como usar o Windows PowerShell para gerenciar o Lync Online, consulte [usando o Windows PowerShell para gerenciar o Lync Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

</div>

<span> </span>

</div>

</div>

</div>

