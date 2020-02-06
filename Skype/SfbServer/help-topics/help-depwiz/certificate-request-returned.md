---
title: Solicitação de Certificado (Retornado)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/1/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertRequestReturned
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4ada9045-0fdf-4470-8574-2fa08bab9392
description: 'A página status da solicitação de certificado online apresenta informações importantes resultantes da criação bem-sucedida e da emissão da solicitação de certificado online. Esta página fornece a impressão digital do certificado que identifica exclusivamente o certificado. Por padrão, a caixa de seleção atribuir este certificado a usos de certificado do Skype for Business Server está selecionada. Se você clicar em concluir, o certificado será atribuído automaticamente ao Lync Server 2013 para fins que você definiu durante as etapas de criação da solicitação de certificado. Por padrão, os fins para os quais o certificado será atribuído são:'
ms.openlocfilehash: 7b4ee3d615de0d0d58e041ba1860cc1cd2d34219
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823805"
---
# <a name="certificate-request-returned"></a><span data-ttu-id="b0742-107">Solicitação de Certificado (Retornado)</span><span class="sxs-lookup"><span data-stu-id="b0742-107">Certificate Request (Returned)</span></span>
 
<span data-ttu-id="b0742-108">A página **status da solicitação de certificado online** apresenta informações importantes resultantes da criação bem-sucedida e da emissão da solicitação de certificado online.</span><span class="sxs-lookup"><span data-stu-id="b0742-108">The **Online Certificate Request Status** page presents you with important information that results from the successful creation and issuing of the online certificate request.</span></span> <span data-ttu-id="b0742-109">Esta página fornece a impressão digital do certificado que identifica exclusivamente o certificado.</span><span class="sxs-lookup"><span data-stu-id="b0742-109">This page provides the certificate thumbprint that uniquely identifies the certificate.</span></span> <span data-ttu-id="b0742-110">Por padrão, a caixa de seleção **atribuir este certificado a usos de certificado do Skype for Business Server** está selecionada.</span><span class="sxs-lookup"><span data-stu-id="b0742-110">By default, the check box **Assign this certificate to Skype for Business Server certificate usages** is selected.</span></span> <span data-ttu-id="b0742-111">Se você clicar em **concluir**, o certificado será atribuído automaticamente ao Lync Server 2013 para fins que você definiu durante as etapas de criação da solicitação de certificado.</span><span class="sxs-lookup"><span data-stu-id="b0742-111">If you click **Finish**, the certificate will be automatically assigned to Lync Server 2013 for the purposes that you defined during the creation steps of the certificate request.</span></span> <span data-ttu-id="b0742-112">Por padrão, os fins para os quais o certificado será atribuído são:</span><span class="sxs-lookup"><span data-stu-id="b0742-112">By default, the purposes that the certificate will be assigned are:</span></span>
  
- <span data-ttu-id="b0742-113">Padrão do servidor para MTLS (Mutual Transport Layer Security)-conexões para clientes e outros servidores</span><span class="sxs-lookup"><span data-stu-id="b0742-113">Server Default for Mutual Transport Layer Security (MTLS) - Connections to clients and other servers</span></span>
    
- <span data-ttu-id="b0742-114">Serviços Web internos-conexões de cliente e servidor no site de serviços Web internos para segurança da camada de transporte/SSL (Secure Sockets Layer)</span><span class="sxs-lookup"><span data-stu-id="b0742-114">Web services internal - Client and server connections on the internal Web services site for Transport Layer Security/Secure Sockets Layer (TLS/SSL)</span></span>
    
- <span data-ttu-id="b0742-115">Conexões de cliente/cliente externo de serviços Web no site de serviços Web externos para TLS/SSL</span><span class="sxs-lookup"><span data-stu-id="b0742-115">Web services external - Client and server connections on the external Web services site for TLS/SSL</span></span>
    
<span data-ttu-id="b0742-116">Clique em **Exibir detalhes do certificado** para exibir o certificado para confirmar que as propriedades do certificado são o que você pretendia e se o certificado está pronto para ser aplicado e colocado em uso no servidor.</span><span class="sxs-lookup"><span data-stu-id="b0742-116">Click the **View Certificate Details** to view the certificate to confirm that the properties of the certificate are what you intended, and that the certificate is ready to be applied and put into use on the server.</span></span>
  
<span data-ttu-id="b0742-117">Clique em **concluir** para concluir o processo de solicitação de certificado online.</span><span class="sxs-lookup"><span data-stu-id="b0742-117">Click **Finish** to complete the online certificate request process.</span></span> <span data-ttu-id="b0742-118">Se você tiver marcado a caixa de seleção **atribuir este certificado aos usos de certificado do Skype for Business Server**, o certificado será atribuído automaticamente.</span><span class="sxs-lookup"><span data-stu-id="b0742-118">If you selected the check box **Assign this certificate to Skype for Business Server certificate usages**, the certificate will be automatically assigned.</span></span> <span data-ttu-id="b0742-119">Se você escolheu desmarcar essa caixa de seleção, deve atribuir o certificado em uma etapa separada.</span><span class="sxs-lookup"><span data-stu-id="b0742-119">If you chose to clear this check box, you must assign the certificate in a separate step.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b0742-120">Se o certificado raiz da CA (autoridade de certificação emitente) não estiver no repositório de autoridade de certificação raiz confiável do computador ou se os certificados de autoridade de certificação intermediários não estiverem na loja apropriada, você verá o status Resumo, conforme ilustrado na imagem a seguir.</span><span class="sxs-lookup"><span data-stu-id="b0742-120">If the issuing certification authority (CA) root certificate is not in the computer's Trusted Root Certification Authority store, or if intermediate CA certificates are not in the proper store, you will see the summary status, as illustrated in the following image.</span></span> <span data-ttu-id="b0742-121">Você não tem a opção de atribuir o certificado.</span><span class="sxs-lookup"><span data-stu-id="b0742-121">You do not have the option to assign the certificate.</span></span> <span data-ttu-id="b0742-122">Para concluir o processo de atribuição de certificado, você deve importar o certificado raiz da CA de emissão e qualquer certificado de CA intermediário e, em seguida, atribuir o certificado clicando em **atribuir** na página do assistente de certificado principal.</span><span class="sxs-lookup"><span data-stu-id="b0742-122">To complete the certificate assignment process, you must import the issuing CA root certificate and any intermediate CA certificates, and then assign the certificate by clicking **Assign** on the main Certificate Wizard page.</span></span>
  

