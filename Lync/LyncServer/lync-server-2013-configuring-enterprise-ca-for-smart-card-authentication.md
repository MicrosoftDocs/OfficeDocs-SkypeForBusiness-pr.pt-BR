---
title: 'Lync Server 2013: Configurando autoridade de certificação corporativa para autenticação de cartão inteligente'
description: 'Lync Server 2013: Configurando autoridade de certificação corporativa para autenticação de cartão inteligente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98044c96dd04d02fd87609918f309cf65227b133
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548437"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Configurando a AC corporativa para autenticação de cartão inteligente no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-07-03_

A seção a seguir descreve como configurar uma autoridade de certificação raiz corporativa para dar suporte à autenticação de cartão inteligente. Para obter informações sobre como instalar uma autoridade de certificação raiz corporativa, consulte instalar uma autoridade de certificação raiz corporativa em [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) .

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurando uma autoridade de certificação raiz corporativa para dar suporte à autenticação de cartão inteligente

As etapas a seguir descrevem como configurar uma autoridade de certificação raiz corporativa para suportar a autenticação de cartão inteligente:

1.  Faça logon no computador de autoridade de certificação corporativa usando uma conta de administrador de domínio.

2.  Inicie o System Manager e verifique se a função de registro da Web da autoridade de certificação está instalada.

3.  No menu **Ferramentas administrativas** , abra o console de gerenciamento de **autoridade de certificação** .

4.  No painel de navegação, expanda **autoridade de certificação**.

5.  Clique com o botão direito em **modelos de certificado**, selecione **novo**e, em seguida, selecione **modelo de certificado a ser emitido**.

6.  Selecione **agente de registro**, **usuário de cartão inteligente**e **logon de cartão inteligente**.

7.  Clique em **OK**.

8.  Clique com o botão direito do mouse em **modelos de certificado**.

9.  Selecione **gerenciar**.

10. Abra as propriedades do modelo de usuário de cartão inteligente.

11. Clique na guia **segurança** .

12. Altere as permissões da seguinte maneira:
    
      - Adicionar contas individuais do AD de usuários com permissões de leitura/registro (permitir) ou
    
      - Adicionar um grupo de segurança contendo usuários de cartões inteligentes com permissões de leitura/registro (permitir) ou
    
      - Adicionar o grupo usuários do domínio com permissões para ler/registrar (permitir)

</div>

</div>

<span> </span>

</div>

</div>

</div>

