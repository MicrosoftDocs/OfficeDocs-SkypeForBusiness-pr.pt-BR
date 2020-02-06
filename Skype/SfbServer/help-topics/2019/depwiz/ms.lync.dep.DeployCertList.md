---
title: Lista de Certificados
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
ROBOTS: NOINDEX, NOFOLLOW
description: Para atribuir um certificado, selecione o certificado no repositório de certificado local. Clique em Avançar para continuar.
ms.openlocfilehash: 23c1da1554b05e04c1491ea43f759b0918ce9d74
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796832"
---
# <a name="certificate-list"></a>Lista de Certificados
 
Para atribuir um certificado, selecione o certificado no repositório de certificado local. Clique em **Avançar** para continuar.
  
O certificado ou certificados disponíveis para seleção no painel **Selecionar um certificado no Armazenamento local de certificados** são certificados válidos que podem ser atribuídos ao uso do certificado necessário. É possível confirmar se o certificado selecionado é o correto clicando no botão **Exibir Detalhes do Certificado**. Na guia **Detalhes**, é possível exibir o nome da entidade e os nomes de entidade alternativos designados como configurados no certificado.
  
> [!IMPORTANT]
> É possível que nenhum certificado esteja listado no painel de seleção. Quando isso ocorre, a causa típica é que não há certificado raiz confiável ou certificados intermediários de autoridade de certificação instalados no servidor pretendido para verificar o certificado e, dessa forma, manter a cadeia de confiança criada pelo certificado para a autoridade de certificação. Para resolver esse problema, solicite e importe uma cadeia de certificados, que normalmente inclui o certificado de autoridade de certificação (AC) raiz e quaisquer certificados de AC intermediária e AC emissora. 
  

