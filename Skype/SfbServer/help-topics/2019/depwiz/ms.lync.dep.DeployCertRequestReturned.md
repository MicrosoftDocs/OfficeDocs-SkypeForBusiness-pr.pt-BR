---
title: Solicitação de Certificado (Retornado)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'A página Status da Solicitação de Certificado Online apresenta informações importantes sobre a criação e emissão bem-sucedida da solicitação de certificado online. Essa página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção Atribuir este certificado a usos de certificados do Skype for Business Server está marcada. Se você clicar em Concluir, o certificado será atribuído automaticamente ao Skype for Business Server para as finalidades definidas durante as etapas de criação da solicitação de certificado. Por padrão, as finalidades as quais o certificado será atribuído são:'
ms.openlocfilehash: 8d7d1dc5013505b7874bccd2ee415f9211713e70
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801831"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="225d4-107">Solicitação de Certificado (Retornado)</span><span class="sxs-lookup"><span data-stu-id="225d4-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="225d4-108">A página **Status da Solicitação de Certificado Online** apresenta informações importantes sobre a criação e emissão bem-sucedida da solicitação de certificado online.</span><span class="sxs-lookup"><span data-stu-id="225d4-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="225d4-109">Essa página fornece a impressão digital do certificado que identifica exclusivamente o certificado.</span><span class="sxs-lookup"><span data-stu-id="225d4-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="225d4-110">Por padrão, a caixa de seleção Atribuir este certificado a usos de **certificados do Skype for Business Server** está marcada.</span><span class="sxs-lookup"><span data-stu-id="225d4-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="225d4-111">Se você clicar **em Concluir,** o certificado será atribuído automaticamente ao Skype for Business Server para as finalidades definidas durante as etapas de criação da solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="225d4-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="225d4-112">Por padrão, as finalidades as quais o certificado será atribuído são:</span><span class="sxs-lookup"><span data-stu-id="225d4-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="225d4-113">Padrão do servidor para MTLS (Mutual Transport Layer Security) - Conexões com clientes e outros servidores</span><span class="sxs-lookup"><span data-stu-id="225d4-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="225d4-114">Serviços Web internos - Conexões de cliente e servidor no site de serviços Web internos para Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="225d4-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="225d4-115">Serviços Web externos - Conexões de cliente e servidor no site de serviços Web externos para TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="225d4-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="225d4-116">Clique em **Exibir detalhes do certificado** para exibir o certificado a fim de confirmar se as propriedades do certificado são o que você pretendia, e se o certificado está pronto para ser aplicado e colocado em uso no servidor.</span><span class="sxs-lookup"><span data-stu-id="225d4-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="225d4-117">Clique em **Concluir** para completar o processo de solicitação de certificado online.</span><span class="sxs-lookup"><span data-stu-id="225d4-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="225d4-118">Se você selecionou a caixa de seleção Atribuir este certificado aos usos de certificados do **Skype for Business Server,** o certificado será atribuído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="225d4-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="225d4-119">Se você escolher desmarcar essa caixa de seleção, será necessário atribuir o certificado em uma etapa separada.</span><span class="sxs-lookup"><span data-stu-id="225d4-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="225d4-120">Se o certificado raiz da autoridade de certificação (CA) de emissão não estiver no armazenamento da Autoridade de Certificação Raiz Confiável do computador ou se os certificados ca intermediários não estão no armazenamento apropriado, você verá o status do resumo, conforme ilustrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="225d4-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="225d4-121">Você não tem a opção de atribuir o certificado.</span><span class="sxs-lookup"><span data-stu-id="225d4-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="225d4-122">Para completar o processo de atribuição do certificado, é necessário importar o certificado raiz CA emissor e quaisquer certificados CA intermediários e atribuir o certificado clicando em **Atribuir** na página principal do Assistente de Certificado.</span><span class="sxs-lookup"><span data-stu-id="225d4-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

