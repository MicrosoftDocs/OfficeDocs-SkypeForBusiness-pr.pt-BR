---
title: Configurar ou Remover Componentes do Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainBootstrap
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: f8813f25-eafa-4006-a186-94e4ebcc5ac7
ROBOTS: NOINDEX, NOFOLLOW
description: 'Para instalar e ativar ou desativar ou desinstalar os componentes do Skype for Business Server, use a Etapa 2: Instalar ou Remover Componentes do Skype Server. Você deve estar conectado como um administrador local no computador que está instalando ou modificando e deve ser capaz de ler usuários e grupos dos Serviços de Domínio Active Directory no domínio atual. Para começar, clique em Executar. Ao fazer isso, a definição de topologia baseada no repositório de Gerenciamento Central é lida. Os componentes de software necessários são instalados e configurados, de acordo com a função, conforme definido no repositório de Gerenciamento Central. Quando a instalação for concluída, revise o Resumo e clique em Concluir.'
ms.openlocfilehash: 8a004e17984a927d08b7c814f8a4ba435c98971e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825042"
---
# <a name="setup-or-remove-skype-for-business-server-components"></a><span data-ttu-id="0022e-108">Configurar ou Remover Componentes do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0022e-108">Setup or Remove Skype for Business Server Components</span></span>
 
<span data-ttu-id="0022e-109">Para instalar e ativar, ou desativar ou desinstalar componentes do Skype for Business Server, use a Etapa **2:** Instalar ou Remover Componentes do Skype Server.</span><span class="sxs-lookup"><span data-stu-id="0022e-109">To install and activate, or deactivate or uninstall Skype for Business Server components, you use **Step 2: Setup or Remove Skype Server Components**.</span></span> <span data-ttu-id="0022e-110">Você deve estar conectado como um administrador local no computador que está instalando ou modificando e deve ser capaz de ler usuários e grupos dos Serviços de Domínio Active Directory no domínio atual.</span><span class="sxs-lookup"><span data-stu-id="0022e-110">You must be logged in as a local administrator on the computer that you are installing or modifying and must be able to read Active Directory Domain Services users and groups in the current domain.</span></span> <span data-ttu-id="0022e-111">Para começar, clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="0022e-111">To begin, click **Run**.</span></span> <span data-ttu-id="0022e-112">Ao fazer isso, a definição de topologia baseada no repositório de Gerenciamento Central é lida.</span><span class="sxs-lookup"><span data-stu-id="0022e-112">When you do this, the Central Management store-based topology definition is read.</span></span> <span data-ttu-id="0022e-113">Os componentes de software necessários são instalados e configurados, de acordo com a função, conforme definido no repositório de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="0022e-113">Necessary software components are installed and configured, according to the role as defined in the Central Management store.</span></span> <span data-ttu-id="0022e-114">Quando a instalação for concluída, revise o Resumo e clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="0022e-114">When the installation is complete, review the Summary, and click **Finish**.</span></span>
  
> [!TIP]
> <span data-ttu-id="0022e-115">Se precisar revisar os arquivos de log criados pelo Assistente de Implantação, você poderá encontrá-los no computador onde o Assistente de Implantação foi executado, no diretório Usuários do usuário do Active Directory que execute a etapa.</span><span class="sxs-lookup"><span data-stu-id="0022e-115">If you need to review the log files that are created by the Deployment Wizard, you can find them on the computer where the Deployment Wizard was run, in the Users directory of the Active Directory user who ran the step.</span></span> <span data-ttu-id="0022e-116">Por exemplo, se o usuário fez logon como administrador de domínio no Contoso.net de domínio, os arquivos de log estão localizados em: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span><span class="sxs-lookup"><span data-stu-id="0022e-116">For example, if the user logged in as the domain administrator in the domain Contoso.net, the log files are located in: > C:\Users\Administrator.Contoso\AppData\Local\Temp</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0022e-117">Se você já instalou componentes do Skype for Business Server neste computador, o Assistente de Implantação reconhecerá isso e o botão na etapa 2 será exibido como Executar **Novamente.**</span><span class="sxs-lookup"><span data-stu-id="0022e-117">If you have previously installed Skype for Business Server components on this computer, the Deployment Wizard will recognize this, and the button in step 2 will be displayed as **Run Again**.</span></span> <span data-ttu-id="0022e-118">Isso permite que você execute a etapa quantas vezes for necessário, a fim de configurar ou modificar corretamente o servidor.</span><span class="sxs-lookup"><span data-stu-id="0022e-118">This enables you to run the step as many times as needed to correctly configure or modify the server.</span></span> 
  

