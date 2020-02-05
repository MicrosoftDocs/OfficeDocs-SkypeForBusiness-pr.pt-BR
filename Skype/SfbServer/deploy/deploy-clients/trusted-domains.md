---
title: Domínios confiáveis do Sistema de Salas do Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leia este tópico para aprender a configurar domínios confiáveis do Sistema de Salas do Skype e do Skype for Business.
ms.openlocfilehash: 618ea5ce6cd4e12cd1e6a811a065f7a29a5c9ced
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768664"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="9be30-103">Domínios confiáveis do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="9be30-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="9be30-104">Leia este tópico para aprender a configurar domínios confiáveis do Sistema de Salas do Skype e do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9be30-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="9be30-105">Domínios confiáveis</span><span class="sxs-lookup"><span data-stu-id="9be30-105">Trusted domains</span></span>

<span data-ttu-id="9be30-106">O cliente Skype for Business exibe uma caixa de diálogo que permite que os usuários aceitem o certificado do servidor do Skype for Business se o domínio SIP da conta de usuário que está entrando for diferente do nome apresentado no nome do assunto ou assunto Alt do assunto no certificado.</span><span class="sxs-lookup"><span data-stu-id="9be30-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="9be30-107">Se o certificado configurado para o Skype for Business Server em sua organização não tiver o nome de domínio SIP da conta do sistema de sala do Skype no assunto ou nome Alt do assunto, você deve configurar esses domínios apresentados no certificado nos domínios confiáveis chave do registro na máquina do console do sistema de sala do Skype.</span><span class="sxs-lookup"><span data-stu-id="9be30-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="9be30-108">O guia do administrador do seu sistema de salas da Skype, fornecido pelo fabricante, explica como e onde adicionar domínios confiáveis ao cliente Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9be30-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="9be30-109">Por exemplo, suponha que os certificados configurados no Skype for Business Server tenham um nome Alt assunto/assunto de "CONTOSO. LOCAL "e um dos domínios SIP atribuídos a um usuário para o endereço de entrada do sistema de sala do Skype é" confrm1@contoso.net ".</span><span class="sxs-lookup"><span data-stu-id="9be30-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="9be30-110">Como o contoso.net não está no certificado, na máquina do sistema de sala do Skype, você precisará configurar "contoso. local" como um domínio confiável no registro, conforme explicado no fabricante do seu sistema de salas da Skype guia do administrador do Skype.</span><span class="sxs-lookup"><span data-stu-id="9be30-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

