---
title: Domínios confiáveis do Sistema de Salas do Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: Leia este tópico para aprender a configurar domínios confiáveis do Sistema de Salas do Skype e do Skype for Business.
ms.openlocfilehash: b55d1558bd45cc8f0726b054fed60b2a4c5e4794
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983760"
---
# <a name="skype-room-system-trusted-domains"></a><span data-ttu-id="a7fa8-103">Domínios confiáveis do Sistema de Salas do Skype</span><span class="sxs-lookup"><span data-stu-id="a7fa8-103">Skype Room System trusted domains</span></span>
 
<span data-ttu-id="a7fa8-104">Leia este tópico para aprender a configurar domínios confiáveis do Sistema de Salas do Skype e do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-104">Read this topic to learn how to configure trusted domains for Skype Room System and Skype for Business.</span></span>
  
## <a name="trusted-domains"></a><span data-ttu-id="a7fa8-105">Domínios confiáveis</span><span class="sxs-lookup"><span data-stu-id="a7fa8-105">Trusted domains</span></span>

<span data-ttu-id="a7fa8-106">O Skype para cliente corporativos exibe uma caixa de diálogo que permite aos usuários aceitar o certificado a partir do Skype para Business Server, se o domínio SIP da conta de usuário entrando for diferente do nome apresentado no assunto ou nome alternativo da entidade do certificado.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-106">The Skype for Business client displays a dialog box that allows users to accept the certificate from the Skype for Business Server if the SIP domain of the user account signing in is different from the name presented in the Subject or Subject Alt Name on the certificate.</span></span> <span data-ttu-id="a7fa8-107">Se o certificado configurado para Skype para Business Server em sua organização não tiver o nome de domínio SIP da conta de sistema do Skype sala no assunto ou nome alternativo da entidade, você deve configurar os domínios apresentados no certificado sob os domínios confiáveis chave do registro na máquina do console do sistema do Skype sala.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-107">If the certificate configured for Skype for Business Server in your organization does not have SIP domain name of Skype Room System account in Subject or Subject Alt Name, you must configure those domains presented on the certificate under the Trusted Domains registry key on the Skype Room System console machine.</span></span> <span data-ttu-id="a7fa8-108">Guia de sistema de sala Skype fornecida pelo fabricante Skype sala do administrador do sistema explica como e onde adicionar domínios confiáveis no Skype para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-108">Your Skype Room System manufacturer-provided Skype Room System Administrator's Guide explains how and where to add trusted domains in the Skype for Business client.</span></span> 
  
<span data-ttu-id="a7fa8-109">Por exemplo, suponha que os certificados configurados no Skype para Business Server têm um nome de Alt do assunto/assunto de "CONTOSO. "LOCAL" e um dos domínios SIP atribuídos a um usuário para o endereço de entrada no sistema de sala do Skype é "confrm1@contoso.net".</span><span class="sxs-lookup"><span data-stu-id="a7fa8-109">For example, assume the certificates configured on Skype for Business Server have a Subject/Subject Alt Name of "CONTOSO.LOCAL" and one of the SIP domains assigned to a user for the Skype Room System sign-in address is "confrm1@contoso.net."</span></span> <span data-ttu-id="a7fa8-110">Porque contoso.net é não no certificado, na máquina do sistema do Skype sala, você precisará configurar "contoso" como um domínio confiável no registro, conforme explicado no guia de sistema de sala Skype fornecida pelo fabricante Skype sala do administrador do sistema.</span><span class="sxs-lookup"><span data-stu-id="a7fa8-110">Because contoso.net is not in the certificate, on the Skype Room System machine, you will need to configure "contoso.local" as a trusted domain in the registry, as explained in your Skype Room System manufacturer-provided Skype Room System Administrator's Guide.</span></span> 
  

