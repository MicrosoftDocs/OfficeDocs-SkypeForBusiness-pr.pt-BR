---
title: Importar Certificado (Introdução)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: Para importar um certificado, forneça um caminho para o arquivo de certificado. Na caixa de texto Selecionar Arquivo de certificado, digite o caminho completo e o nome do arquivo, ou clique no botão Procurar e navegue até o local do caminho e o nome do arquivo (normalmente, um arquivo .p7b, .pfx ou .cer).
ms.openlocfilehash: 2ca89291376c488426001e1ff42c4925da58a3e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827281"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="e4d8c-104">Importar Certificado (Introdução)</span><span class="sxs-lookup"><span data-stu-id="e4d8c-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="e4d8c-p102">Para importar um certificado, forneça um caminho para o arquivo de certificado. Na caixa de texto **Selecionar Arquivo de certificado**, digite o caminho completo e o nome do arquivo, ou clique no botão **Procurar** e navegue até o local do caminho e o nome do arquivo (normalmente, um arquivo .p7b, .pfx ou .cer).</span><span class="sxs-lookup"><span data-stu-id="e4d8c-p102">To import a certificate, you must provide a path to the certificate file. In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="e4d8c-107">Se o certificado contiver uma chave privada, marque a caixa de seleção O arquivo de certificado **contém a chave privada do certificado.**</span><span class="sxs-lookup"><span data-stu-id="e4d8c-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="e4d8c-108">Quando esta caixa de seleção está marcada, o campo de texto **Senha** é habilitado.</span><span class="sxs-lookup"><span data-stu-id="e4d8c-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="e4d8c-109">Uma senha normalmente é colocada na chave privada quando o certificado é criado, caso você possua um certificado com uma chave privada associada a ele.</span><span class="sxs-lookup"><span data-stu-id="e4d8c-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="e4d8c-110">Digite a senha para a chave privada a fim de permitir que o certificado e a chave privada sejam importados para o repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="e4d8c-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="e4d8c-111">Depois de fornecer as informações para o caminho do arquivo de certificado e, opcionalmente, a senha da chave privada, se for necessário, clique em **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e4d8c-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e4d8c-112">Se você não souber a senha para a chave privada, a importação falhará.</span><span class="sxs-lookup"><span data-stu-id="e4d8c-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

