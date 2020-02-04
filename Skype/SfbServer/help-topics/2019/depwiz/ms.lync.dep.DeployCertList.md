---
title: Lista de Certificados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
ROBOTS: NOINDEX, NOFOLLOW
description: Para atribuir um certificado, selecione o certificado no repositório de certificado local. Clique em Avançar para continuar.
ms.openlocfilehash: 11dc4afa39ecf232e509f306d4f7bd5f33f12dd2
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41692156"
---
# <a name="certificate-list"></a><span data-ttu-id="30708-104">Lista de Certificados</span><span class="sxs-lookup"><span data-stu-id="30708-104">Certificate List</span></span>
 
<span data-ttu-id="30708-p102">Para atribuir um certificado, selecione o certificado no repositório de certificado local. Clique em **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="30708-p102">To assign a certificate, select a certificate from the local certificate store. Click **Next** to continue.</span></span>
  
<span data-ttu-id="30708-p103">O certificado ou certificados disponíveis para seleção no painel **Selecionar um certificado no Armazenamento local de certificados** são certificados válidos que podem ser atribuídos ao uso do certificado necessário. É possível confirmar se o certificado selecionado é o correto clicando no botão **Exibir Detalhes do Certificado**. Na guia **Detalhes**, é possível exibir o nome da entidade e os nomes de entidade alternativos designados como configurados no certificado.</span><span class="sxs-lookup"><span data-stu-id="30708-p103">The certificate or certificates that are available for selection in the **Select a certificate from the local certificate store** pane are valid certificates that can be assigned to the certificate usage that you need. You can confirm that the certificate that you select is the correct one by clicking the **View Certificate Details** button. On the **Details** tab, you can view the subject name and subject alternatives designated as configured on the certificate.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="30708-p104">É possível que nenhum certificado esteja listado no painel de seleção. Quando isso ocorre, a causa típica é que não há certificado raiz confiável ou certificados intermediários de autoridade de certificação instalados no servidor pretendido para verificar o certificado e, dessa forma, manter a cadeia de confiança criada pelo certificado para a autoridade de certificação. Para resolver esse problema, solicite e importe uma cadeia de certificados, que normalmente inclui o certificado de autoridade de certificação (AC) raiz e quaisquer certificados de AC intermediária e AC emissora.</span><span class="sxs-lookup"><span data-stu-id="30708-p104">It is possible that no certificate will be listed in the selection pane. When this occurs, the typical cause is that there are no trusted root certificate or intermediate certification authority certificates installed on the intended server to verify the certificate and therefore maintain the chain of trust created by the certificate to the certification authority. To resolve this issue, request and import a certificate chain, which typically includes the root certification authority (CA) certificate and any intermediate CA certificates and issuing CA certificates.</span></span> 
  

