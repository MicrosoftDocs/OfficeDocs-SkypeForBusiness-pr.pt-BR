---
title: Configurar o repositório de contatos pessoais em computadores cliente para o Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ec69a6cb-07f2-4057-9544-55035f83eeae
description: 'Resumo: Configure o repositório de contatos pessoal usado pelo Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server 2015.'
ms.openlocfilehash: 6d6c34a196e418d66708418ff8805caf19d39cfe
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-the-personal-contacts-store-on-client-computers-for-skype-for-business-server-2015"></a><span data-ttu-id="257b9-103">Configurar o repositório de contatos pessoais em computadores cliente para o Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="257b9-103">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="257b9-104">**Resumo:** Configure o armazenamento de contato pessoal usado pelo Exchange Server 2016 ou Exchange Server 2013 e Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="257b9-104">**Summary:** Configure the personal contact store used by Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="257b9-105">Se você estiver integrando Skype para Business Server 2015 e Exchange Server 2016 ou Exchange Server 2013, você deverá configurar o armazenamento de contato pessoal em todos os computadores cliente com Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="257b9-105">If you are integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, then you should configure the personal contact store on any client computers running Skype for Business.</span></span> <span data-ttu-id="257b9-106">Em particular, você deve configurar Skype para a usar o Exchange como o armazenamento de contato pessoal e, ao mesmo tempo, certifique-se de que os usuários não sejam capazes de substituir essa decisão de negócios.</span><span class="sxs-lookup"><span data-stu-id="257b9-106">In particular, you should configure Skype for Business to use Exchange as the personal contact store, and, at the same time, ensure that users are not able to override that decision.</span></span> <span data-ttu-id="257b9-107">Isso pode ser feito com a criação e configuração de um valor de Registro em cada computador cliente.</span><span class="sxs-lookup"><span data-stu-id="257b9-107">This can be done by creating and configuring a Registry value on each client computer.</span></span>
  
<span data-ttu-id="257b9-108">Observe que isso não é necessário em computadores que executam o Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="257b9-108">Note that this is not required on computers running Skype for Business.</span></span>
  
<span data-ttu-id="257b9-109">Para configurar esse valor em um único computador, execute os seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="257b9-109">To configure this value on a single computer, complete the following procedure:</span></span>
  
1. <span data-ttu-id="257b9-110">No computador do cliente, clique em **Iniciar**, e então clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="257b9-110">On the client computer, click **Start** and then click **Run**.</span></span>
    
2. <span data-ttu-id="257b9-111">Na caixa de diálogo **Executar**, digite regedit e depois pressione ENTER.</span><span class="sxs-lookup"><span data-stu-id="257b9-111">In the **Run** dialog box, type regedit and then press ENTER.</span></span>
    
3. <span data-ttu-id="257b9-112">No Editor de Registro, expanda **HKEY_LOCAL_MACHINE**, expanda **Software**, expanda **Policies**, expanda **Microsoft** e expanda **Communicator**.</span><span class="sxs-lookup"><span data-stu-id="257b9-112">In Registry Editor, expand **HKEY_LOCAL_MACHINE**, expand **Software**, expand **Policies**, expand **Microsoft**, and then expand **Communicator**.</span></span>
    
4. <span data-ttu-id="257b9-113">Clique com o botão direito do mouse em **Communicator**, aponte para **Novo** e clique no **Valor DWORD (32 bits)**.</span><span class="sxs-lookup"><span data-stu-id="257b9-113">Right-click **Communicator**, point to **New**, and then click **DWORD (32-bit) Value**.</span></span>
    
5. <span data-ttu-id="257b9-114">Depois que o novo valor é criado, digite PersonalContactStoreOverride e pressione ENTER para renomear o valor.</span><span class="sxs-lookup"><span data-stu-id="257b9-114">After the new value is created, type PersonalContactStoreOverride and then press ENTER to rename the value.</span></span>
    
6. <span data-ttu-id="257b9-115">Verifique se o valor de PersonalContactStoreOverride está definido para 0 e feche o Editor do Registro.</span><span class="sxs-lookup"><span data-stu-id="257b9-115">Verify that the value of PersonalContactStoreOverride is set to 0 and then close Registry Editor.</span></span>
    
<span data-ttu-id="257b9-116">Se precisar fazer esta mesma alteração em vários computadores, você pode criar um objeto personalizado de Política de Grupo.</span><span class="sxs-lookup"><span data-stu-id="257b9-116">If you need to make this same change on multiple computers you can do so by creating a custom Group Policy object.</span></span> <span data-ttu-id="257b9-117">Para obter detalhes, consulte a documentação de diretiva de grupo em [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span><span class="sxs-lookup"><span data-stu-id="257b9-117">For details, see the Group Policy documentation at [https://go.microsoft.com/fwlink/p/?LinkId=268543](https://go.microsoft.com/fwlink/p/?LinkId=268543).</span></span>
  

