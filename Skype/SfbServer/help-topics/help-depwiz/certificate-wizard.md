---
title: Assistente de Certificado
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: Para Solicitar, Atribuir, Remover ou Exibir certificados, use o Assistente de Certificado. É necessário estar conectado como membro do grupo RTCUniversalServerAdmins. Para solicitar um certificado de uma autoridade de certificação (AC) pública, não são necessárias quaisquer associações de grupo adicionais. Para solicitar um certificado da infraestrutura de chave pública (PKI) da sua organização, você precisa confirmar o que será adicional, se for o caso, você precisará de associações de grupo. Durante a tarefa de solicitação, você pode inserir credenciais alternativas que serão usadas para solicitar o certificado da CA de emissão da sua PKI.
ms.openlocfilehash: 0ae4a9f5bf80cc33cd743349c5353f40f2fdb986
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34301901"
---
# <a name="certificate-wizard"></a><span data-ttu-id="3bed0-107">Assistente de Certificado</span><span class="sxs-lookup"><span data-stu-id="3bed0-107">Certificate Wizard</span></span>
 
<span data-ttu-id="3bed0-108">Para **Solicitar**, **Atribuir**, **Remover** ou **Exibir** certificados, use o Assistente de Certificado.</span><span class="sxs-lookup"><span data-stu-id="3bed0-108">To **Request**, **Assign**, **Remove**, or **View** certificates, you use the Certificate Wizard.</span></span> <span data-ttu-id="3bed0-109">É necessário estar conectado como membro do grupo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="3bed0-109">You must be logged in as a member of the RTCUniversalServerAdmins group.</span></span> <span data-ttu-id="3bed0-110">Para solicitar um certificado de uma autoridade de certificação (AC) pública, não são necessárias quaisquer associações de grupo adicionais.</span><span class="sxs-lookup"><span data-stu-id="3bed0-110">To request a certificate from a public certification authority (CA), you do not need any additional group memberships.</span></span> <span data-ttu-id="3bed0-111">Para solicitar um certificado da infraestrutura de chave pública (PKI) da sua organização, você precisa confirmar o que será adicional, se for o caso, você precisará de associações de grupo.</span><span class="sxs-lookup"><span data-stu-id="3bed0-111">To request a certificate from your organization's public key infrastructure (PKI), you need to confirm what additional—if any—group memberships you will need.</span></span> <span data-ttu-id="3bed0-112">Durante a tarefa de solicitação, você pode inserir credenciais alternativas que serão usadas para solicitar o certificado da CA de emissão da sua PKI.</span><span class="sxs-lookup"><span data-stu-id="3bed0-112">During the Request task, you can enter alternate credentials that will be used to request the certificate from your PKI's issuing CA.</span></span>
  
<span data-ttu-id="3bed0-113">Para solicitar um novo certificado, clique em **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="3bed0-113">To request a new certificate, click **Request**.</span></span>
  
<span data-ttu-id="3bed0-114">Para atribuir um certificado que ainda não foi atribuído, clique em **Atribuir**.</span><span class="sxs-lookup"><span data-stu-id="3bed0-114">To assign a certificate that has not been assigned yet, click **Assign**.</span></span>
  
<span data-ttu-id="3bed0-115">Para remover um certificado atribuído anteriormente, clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="3bed0-115">To remove a certificate that you have previously assigned, click **Remove**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3bed0-p103">O botão **Remover** estará disponível somente se um certificado tiver sido atribuído anteriormente. Se o botão **Remover** não estiver disponível (esmaecido), então não há certificado atribuído.</span><span class="sxs-lookup"><span data-stu-id="3bed0-p103">The **Remove** button will be available only if a certificate has been previously assigned. If the **Remove** button is unavailable (dimmed), there is no certificate assigned.</span></span>
  
<span data-ttu-id="3bed0-118">Para exibir um certificado atribuído, clique em **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="3bed0-118">To view an assigned certificate, click **View**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3bed0-p104">O botão **Exibir** estará disponível somente se um certificado tiver sido atribuído anteriormente. Se o botão **Exibir** estiver esmaecido, então não há certificado atribuído.</span><span class="sxs-lookup"><span data-stu-id="3bed0-p104">The **View** button will be available only if a certificate has been previously assigned. If the **View** button is greyed out, there is no certificate assigned.</span></span>
  
<span data-ttu-id="3bed0-121">Para atualizar a tela atual de atribuição de certificado, clique em **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="3bed0-121">To refresh the current certificate assignment screen, click **Refresh**.</span></span>
  
<span data-ttu-id="3bed0-122">Para importar um certificado que não está presente no repositório de certificados, clique em **Importar Certificado**.</span><span class="sxs-lookup"><span data-stu-id="3bed0-122">To import a certificate that is not present in the certificate store, click **Import Certificate**.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3bed0-123">**Importar Certificado** é normalmente usado para processar um certificado recebido por meio de um processo diferente de uma solicitação do Assistente de Certificado.</span><span class="sxs-lookup"><span data-stu-id="3bed0-123">**Import Certificate** is typically used to process a certificate that is received through a process other than a request from the Certificate Wizard.</span></span> <span data-ttu-id="3bed0-124">Por exemplo, seu administrador de PKI cria um certificado e o disponibiliza a você.</span><span class="sxs-lookup"><span data-stu-id="3bed0-124">For example, your PKI administrator creates a certificate and makes it available to you.</span></span> <span data-ttu-id="3bed0-125">Use **importar certificado** para importar o certificado para o repositório de certificados do computador e torná-lo disponível para o Skype for Business Server atribuir.</span><span class="sxs-lookup"><span data-stu-id="3bed0-125">Use **Import Certificate** to import the certificate into the computer's certificate store and make it available to Skype for Business Server to assign.</span></span>
  
<span data-ttu-id="3bed0-p106">Para completar o processo de solicitação de uma solicitação de certificado de uma AC em sua organização que exige aprovação do administrador de AC, clique em **Processar Solicitação Pendente**. A solicitação de certificado retornará um status de pendente e também exibirá o número de identificação da solicitação pendente. Para continuar processando um certificado com um status de pendente, clique em **Atualizar** para habilitar o botão **Processar Solicitação Pendente**. O botão **Processar Solicitação Pendente** não ficará mais indisponível (esmaecido). Dessa forma, é possível tentar recuperar a solicitação pendente, mas o status da solicitação permanecerá pendente até que o certificado seja emitido ou negado pelo administrador da AC. O botão ficará indisponível se não houver solicitações pendentes válidas criadas pelo Assistente de Certificado.</span><span class="sxs-lookup"><span data-stu-id="3bed0-p106">To complete the process of requesting a certificate request from a CA in your organization that requires CA administrator approval, click **Process Pending Request**. The certificate request will have returned a status of pending, and also displays the identification number of the pending request. To continue processing a certificate with a pending status, click **Refresh** to enable the **Process Pending Request** button. The **Process Pending Request** button will no longer be unavailable (dimmed). You can then attempt to retrieve the pending request, but the status of the request will remain pending until the certificate is issued or denied by the CA administrator. The button will be unavailable if there are no valid pending requests that have been created by the Certificate Wizard.</span></span>
  

