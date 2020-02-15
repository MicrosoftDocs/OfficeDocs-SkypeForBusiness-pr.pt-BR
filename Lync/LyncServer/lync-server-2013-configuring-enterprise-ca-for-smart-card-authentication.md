---
title: 'Lync Server 2013: Configurando autoridade de certificação corporativa para autenticação de cartão inteligente'
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
ms.openlocfilehash: a49fb76019fbb3bc3356fed5de7a67b0e3a10350
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046374"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="ec624-102">Configurando a AC corporativa para autenticação de cartão inteligente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec624-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec624-103">_**Última modificação do tópico:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="ec624-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="ec624-104">A seção a seguir descreve como configurar uma autoridade de certificação raiz corporativa para dar suporte à autenticação de cartão inteligente.</span><span class="sxs-lookup"><span data-stu-id="ec624-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="ec624-105">Para obter informações sobre como instalar uma autoridade de certificação raiz corporativa, consulte instalar uma autoridade de certificação [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)raiz corporativa em.</span><span class="sxs-lookup"><span data-stu-id="ec624-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="ec624-106">Configurando uma autoridade de certificação raiz corporativa para dar suporte à autenticação de cartão inteligente</span><span class="sxs-lookup"><span data-stu-id="ec624-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="ec624-107">As etapas a seguir descrevem como configurar uma autoridade de certificação raiz corporativa para suportar a autenticação de cartão inteligente:</span><span class="sxs-lookup"><span data-stu-id="ec624-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="ec624-108">Faça logon no computador de autoridade de certificação corporativa usando uma conta de administrador de domínio.</span><span class="sxs-lookup"><span data-stu-id="ec624-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="ec624-109">Inicie o System Manager e verifique se a função de registro da Web da autoridade de certificação está instalada.</span><span class="sxs-lookup"><span data-stu-id="ec624-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="ec624-110">No menu **Ferramentas administrativas** , abra o console de gerenciamento de **autoridade de certificação** .</span><span class="sxs-lookup"><span data-stu-id="ec624-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="ec624-111">No painel de navegação, expanda **autoridade de certificação**.</span><span class="sxs-lookup"><span data-stu-id="ec624-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="ec624-112">Clique com o botão direito em **modelos de certificado**, selecione **novo**e, em seguida, selecione **modelo de certificado a ser emitido**.</span><span class="sxs-lookup"><span data-stu-id="ec624-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="ec624-113">Selecione **agente de registro**, **usuário de cartão inteligente**e **logon de cartão inteligente**.</span><span class="sxs-lookup"><span data-stu-id="ec624-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="ec624-114">Clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ec624-114">Click **OK**.</span></span>

8.  <span data-ttu-id="ec624-115">Clique com o botão direito do mouse em **modelos de certificado**.</span><span class="sxs-lookup"><span data-stu-id="ec624-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="ec624-116">Selecione **gerenciar**.</span><span class="sxs-lookup"><span data-stu-id="ec624-116">Select **Manage**.</span></span>

10. <span data-ttu-id="ec624-117">Abra as propriedades do modelo de usuário de cartão inteligente.</span><span class="sxs-lookup"><span data-stu-id="ec624-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="ec624-118">Clique na guia **segurança** .</span><span class="sxs-lookup"><span data-stu-id="ec624-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="ec624-119">Altere as permissões da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="ec624-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="ec624-120">Adicionar contas individuais do AD de usuários com permissões de leitura/registro (permitir) ou</span><span class="sxs-lookup"><span data-stu-id="ec624-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="ec624-121">Adicionar um grupo de segurança contendo usuários de cartões inteligentes com permissões de leitura/registro (permitir) ou</span><span class="sxs-lookup"><span data-stu-id="ec624-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="ec624-122">Adicionar o grupo usuários do domínio com permissões para ler/registrar (permitir)</span><span class="sxs-lookup"><span data-stu-id="ec624-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

