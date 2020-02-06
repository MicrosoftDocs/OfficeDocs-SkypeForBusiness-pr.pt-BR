---
title: Configurar o repositório de contatos pessoais em computadores cliente do Lync 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/29/2019
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumo: configurar o repositório de contatos pessoal usado pelos clientes herdados.'
ms.openlocfilehash: a80af6ca575b53e5a2b8f77a109fd6929f0db704
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797022"
---
# <a name="configure-the-personal-contacts-store-on-lync-2010-client-computers"></a><span data-ttu-id="7c580-103">Configurar o repositório de contatos pessoais em computadores cliente do Lync 2010</span><span class="sxs-lookup"><span data-stu-id="7c580-103">Configure the personal contacts store on Lync 2010 client computers</span></span>
  
<span data-ttu-id="7c580-104">Se você estiver integrando o Skype for Business Server 2015 e o servidor do Exchange 2016 ou Exchange Server 2013, configure o repositório de contatos pessoal usado pelos clientes.</span><span class="sxs-lookup"><span data-stu-id="7c580-104">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store used by the clients.</span></span> <span data-ttu-id="7c580-105">Em particular, você deve configurar o Skype for Business para usar o Exchange como o repositório de contatos pessoais e, ao mesmo tempo, garantir que os usuários não consigam substituir essa decisão.</span><span class="sxs-lookup"><span data-stu-id="7c580-105">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="7c580-106">Isso pode ser feito com a criação e configuração de um valor de Registro em cada computador cliente.</span><span class="sxs-lookup"><span data-stu-id="7c580-106">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7c580-107">O procedimento a seguir só é necessário para clientes que usam o cliente Lync 2010 ou anterior.</span><span class="sxs-lookup"><span data-stu-id="7c580-107">The following procedure is only necessary for clients using the Lync 2010 client or earlier.</span></span> <span data-ttu-id="7c580-108">O cliente do Lync 2013 e todos os clientes do Skype for Business não terão a opção de substituir as configurações da loja de contatos.</span><span class="sxs-lookup"><span data-stu-id="7c580-108">The Lync 2013 client and all Skype for Business clients will not have the option of overriding the contact store settings.</span></span>
  
<span data-ttu-id="7c580-109">Para configurar esse valor em um único computador, execute os seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="7c580-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="7c580-110">No computador do cliente, clique em **Iniciar**, e então clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7c580-110">On the client computer, click **Start** and then click **Run**.</span></span>
2. <span data-ttu-id="7c580-111">Na caixa de diálogo **Executar**, digite regedit e depois pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="7c580-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
3. <span data-ttu-id="7c580-112">No Editor de Registro, expanda **HKEY_LOCAL_MACHINE**, expanda **Software**, expanda **Policies**, expanda **Microsoft** e expanda **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="7c580-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
4. <span data-ttu-id="7c580-113">Clique com o botão direito do mouse em **Communicator**, aponte para **Novo** e clique no **Valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="7c580-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
5. <span data-ttu-id="7c580-114">Depois do novo valor ser criado, digite PersonalContactStoreOverride e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="7c580-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
6. <span data-ttu-id="7c580-115">Verifique se o valor de PersonalContactStoreOverride está definido para 0 e feche o Editor do Registro.</span><span class="sxs-lookup"><span data-stu-id="7c580-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>

<span data-ttu-id="7c580-116">Se precisar fazer esta mesma alteração em vários computadores, você pode criar um objeto personalizado de Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="7c580-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="7c580-117">Para obter detalhes sobre como fazer isso no Windows 10, consulte o artigo [criar um objeto de política de grupo](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) .</span><span class="sxs-lookup"><span data-stu-id="7c580-117">For details on doing this in Windows 10, see the [Create a Group Policy Object](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/create-a-group-policy-object) article.</span></span>
  
