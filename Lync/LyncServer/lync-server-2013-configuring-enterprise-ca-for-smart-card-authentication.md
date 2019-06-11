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

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="a3097-102">Configurando a CA corporativa para autenticação de cartão inteligente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a3097-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a3097-103">_**Tópico da última modificação:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="a3097-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="a3097-104">A seção a seguir descreve como configurar uma CA (autoridade de certificação) raiz corporativa para dar suporte à autenticação de cartão inteligente.</span><span class="sxs-lookup"><span data-stu-id="a3097-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="a3097-105">Para obter informações sobre como instalar uma autoridade de certificação raiz corporativa, consulte instalar uma autoridade de certificação [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)raiz corporativa em.</span><span class="sxs-lookup"><span data-stu-id="a3097-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="a3097-106">Configurando uma autoridade de certificação raiz corporativa para dar suporte à autenticação de cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="a3097-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="a3097-107">As seguintes etapas descrevem como configurar uma CA Raiz Corporativa para dar suporte à Autenticação de Cartão Inteligente:</span><span class="sxs-lookup"><span data-stu-id="a3097-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="a3097-108">Faça o login no computador da AC corporativa utilizando uma conta de Administrador de Domínio.</span><span class="sxs-lookup"><span data-stu-id="a3097-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="a3097-109">Inicie o Gerenciador de Sistema e verifique se a função de Registro da Web da Autoridade de Certificação está instalada.</span><span class="sxs-lookup"><span data-stu-id="a3097-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="a3097-110">No menu **Ferramentas Administrativas**, abra o console de gerenciamento da **Autoridade de Certificação**.</span><span class="sxs-lookup"><span data-stu-id="a3097-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="a3097-111">No painel de Navegação, expanda **Autoridade de Certificação**.</span><span class="sxs-lookup"><span data-stu-id="a3097-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="a3097-112">Clique com o botão direito do mouse em **Modelos de Certificado**, selecione **Novo** e, em seguida, selecione **Modelo de Certificação para Emissão**.</span><span class="sxs-lookup"><span data-stu-id="a3097-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="a3097-113">Selecione **Agente de Registro**, **Usuário do Cartão Inteligente** e **Logon do Cartão Inteligente**.</span><span class="sxs-lookup"><span data-stu-id="a3097-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="a3097-114">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="a3097-114">Click **OK**.</span></span>

8.  <span data-ttu-id="a3097-115">Clique com o botão direito em **Modelos de Certificado**.</span><span class="sxs-lookup"><span data-stu-id="a3097-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="a3097-116">Selecione **Gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="a3097-116">Select **Manage**.</span></span>

10. <span data-ttu-id="a3097-117">Abra as propriedades do modelo do Usuário do Cartão Inteligente.</span><span class="sxs-lookup"><span data-stu-id="a3097-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="a3097-118">Clique na guia **Segurança**.</span><span class="sxs-lookup"><span data-stu-id="a3097-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="a3097-119">Altere as permissões da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="a3097-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="a3097-120">Adicione contas de AD de usuários individuais com permissões para Ler/Registrar (Permitir) ou</span><span class="sxs-lookup"><span data-stu-id="a3097-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="a3097-121">Adicione um grupo de segurança contendo usuários do cartão inteligente com permissões para Ler/Registrar (Permitir), ou</span><span class="sxs-lookup"><span data-stu-id="a3097-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="a3097-122">Adicione o grupo do Usuário de Domínio com as permissões para Ler/Registrar (Permitir)</span><span class="sxs-lookup"><span data-stu-id="a3097-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

