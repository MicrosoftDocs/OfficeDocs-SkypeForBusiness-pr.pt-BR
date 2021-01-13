---
title: Domínios confiáveis do Sistema de Sala do Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leia este tópico para saber como configurar domínios confiáveis para o Sistema de Sala do Skype e o Skype for Business.
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834111"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="a5dcc-103">Domínios confiáveis do Sistema de Sala do Skype</span><span class="sxs-lookup"><span data-stu-id="a5dcc-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="a5dcc-104">Leia este tópico para saber como configurar domínios confiáveis para o Sistema de Sala do Skype e o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a5dcc-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="a5dcc-105">Domínios confiáveis</span><span class="sxs-lookup"><span data-stu-id="a5dcc-105">Trusted domains</span></span>

<span data-ttu-id="a5dcc-106">O cliente Skype for Business exibe uma caixa de diálogo que permite que os usuários aceitem o certificado do Skype for Business Server se o domínio SIP da conta de usuário que está se inando for diferente do nome apresentado no Assunto ou nome Alt da Assunto no certificado.</span><span class="sxs-lookup"><span data-stu-id="a5dcc-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="a5dcc-107">Se o certificado configurado para o Skype for Business Server em sua organização não tiver o nome de domínio SIP da conta do Sistema de Sala do Skype em Assunto ou Nome Alt da Entidade, você deverá configurar esses domínios apresentados no certificado sob a chave do Registro de Domínios Confiáveis na máquina de console do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="a5dcc-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="a5dcc-108">O Guia do Administrador do Sistema de Sala do Skype fornecido pelo fabricante do Sistema de Sala do Skype explica como e onde adicionar domínios confiáveis no cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a5dcc-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="a5dcc-109">Por exemplo, suponha que os certificados configurados no Skype for Business Server tenham um Nome Alt assunto/assunto de "CONTOSO. LOCAL" e um dos domínios SIP atribuídos a um usuário para o endereço de login do Sistema de Sala do Skype é "confrm1@contoso.net".</span><span class="sxs-lookup"><span data-stu-id="a5dcc-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="a5dcc-110">Como o contoso.net não está no certificado, na máquina do Sistema de Sala do Skype, você precisará configurar "contoso.local" como um domínio confiável no registro, conforme explicado no Guia do Administrador do Sistema de Sala do Skype fornecido pelo fabricante do Sistema de Sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="a5dcc-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

