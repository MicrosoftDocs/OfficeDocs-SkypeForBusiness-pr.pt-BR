---
title: Solicitação de certificado (retornada)
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
ROBOTS: NOINDEX, NOFOLLOW
description: 'A página Status da solicitação de certificado Online apresenta informações importantes que resulta de êxito na criação e emissão da solicitação de certificado online. Esta página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção atribuir esse certificado para Skype para usos de certificado de servidor de negócios está selecionada. Se você clicar em Concluir, o certificado será automaticamente atribuído para Skype para Business Server para as finalidades que você definiu durante as etapas de criação da solicitação de certificado. Por padrão, as finalidades que o certificado será atribuído são:'
ms.openlocfilehash: 2de8bae390ed8406883f5c6cd74709990c6c450b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20983753"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="4b5af-107">Solicitação de certificado (retornada)</span><span class="sxs-lookup"><span data-stu-id="4b5af-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="4b5af-108">A página **Status da solicitação de certificado Online** apresenta informações importantes que resulta de êxito na criação e emissão da solicitação de certificado online.</span><span class="sxs-lookup"><span data-stu-id="4b5af-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="4b5af-109">Esta página fornece a impressão digital do certificado que identifica exclusivamente o certificado.</span><span class="sxs-lookup"><span data-stu-id="4b5af-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="4b5af-110">Por padrão, a caixa de seleção **atribuir este certificado Skype para usos de certificado de servidor de negócios** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="4b5af-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="4b5af-111">Se você clicar em **Concluir**, o certificado será automaticamente atribuído para Skype para Business Server para as finalidades que você definiu durante as etapas de criação da solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="4b5af-111">If you click **Finish**, the certificate will be automatically assigned to Skype for Business Server for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="4b5af-112">Por padrão, as finalidades que o certificado será atribuído são:</span><span class="sxs-lookup"><span data-stu-id="4b5af-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="4b5af-113">Padrão de servidor para Mutual Transport Layer Security (MTLS) - conexões com clientes e outros servidores</span><span class="sxs-lookup"><span data-stu-id="4b5af-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="4b5af-114">Serviços Web internos - site de serviços de conexões de cliente e servidor na Web interna para Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span><span class="sxs-lookup"><span data-stu-id="4b5af-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="4b5af-115">Serviços Web externos - site de serviços de conexões de cliente e servidor na Web externa para TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="4b5af-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="4b5af-116">Clique em **Exibir detalhes de certificados** para exibir o certificado para confirmar que as propriedades do certificado são o que você pretendia e que o certificado está pronto para ser aplicada e colocar em uso no servidor.</span><span class="sxs-lookup"><span data-stu-id="4b5af-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="4b5af-117">Clique em **Concluir** para concluir o processo de solicitação de certificado online.</span><span class="sxs-lookup"><span data-stu-id="4b5af-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="4b5af-118">Se você marcou a caixa de seleção **atribuir este certificado Skype para usos de certificado de servidor de negócios**, o certificado será atribuído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4b5af-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="4b5af-119">Se você optar por desmarcar essa caixa, você deve atribuir o certificado em uma etapa separada.</span><span class="sxs-lookup"><span data-stu-id="4b5af-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="4b5af-120">Se o certificado de raiz de autoridade de certificação emissora não estiver no repositório de autoridade de certificação raiz confiáveis do computador, ou se certificados de autoridade de certificação intermediários não estão no repositório de adequado, você verá o status de resumo, como ilustrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="4b5af-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="4b5af-121">Você não tem a opção para atribuir o certificado.</span><span class="sxs-lookup"><span data-stu-id="4b5af-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="4b5af-122">Para concluir o processo de atribuição de certificado, você deve importar o certificado de raiz da autoridade de certificação emissora e qualquer certificados de autoridade de certificação intermediários e, em seguida, atribuir o certificado clicando em **atribuir** na página principal do Assistente de certificado.</span><span class="sxs-lookup"><span data-stu-id="4b5af-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

