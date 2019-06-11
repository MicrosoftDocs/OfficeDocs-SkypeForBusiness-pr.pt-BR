---
title: 'Lync Server 2013: Configurando a CA empresarial para autenticação de cartão inteligente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 890a69d1c863702db0a70cfb2ce3d61f6a75eeae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a>Configurando a CA corporativa para autenticação de cartão inteligente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-07-03_

A seção a seguir descreve como configurar uma CA (autoridade de certificação) raiz corporativa para dar suporte à autenticação de cartão inteligente. Para obter informações sobre como instalar uma autoridade de certificação raiz corporativa, consulte instalar uma autoridade de certificação [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)raiz corporativa em.

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a>Configurando uma autoridade de certificação raiz corporativa para dar suporte à autenticação de cartão inteligente

As seguintes etapas descrevem como configurar uma CA Raiz Corporativa para dar suporte à Autenticação de Cartão Inteligente:

1.  Faça o login no computador da AC corporativa utilizando uma conta de Administrador de Domínio.

2.  Inicie o Gerenciador de Sistema e verifique se a função de Registro da Web da Autoridade de Certificação está instalada.

3.  No menu **Ferramentas Administrativas**, abra o console de gerenciamento da **Autoridade de Certificação**.

4.  No painel de Navegação, expanda **Autoridade de Certificação**.

5.  Clique com o botão direito do mouse em **Modelos de Certificado**, selecione **Novo** e, em seguida, selecione **Modelo de Certificação para Emissão**.

6.  Selecione **Agente de Registro**, **Usuário do Cartão Inteligente** e **Logon do Cartão Inteligente**.

7.  Clique em **OK**.

8.  Clique com o botão direito em **Modelos de Certificado**.

9.  Selecione **Gerenciar**.

10. Abra as propriedades do modelo do Usuário do Cartão Inteligente.

11. Clique na guia **Segurança**.

12. Altere as permissões da seguinte forma:
    
      - Adicione contas de AD de usuários individuais com permissões para Ler/Registrar (Permitir) ou
    
      - Adicione um grupo de segurança contendo usuários do cartão inteligente com permissões para Ler/Registrar (Permitir), ou
    
      - Adicione o grupo do Usuário de Domínio com as permissões para Ler/Registrar (Permitir)

</div>

</div>

<span> </span>

</div>

</div>

</div>

