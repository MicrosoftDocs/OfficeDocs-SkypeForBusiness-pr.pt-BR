---
title: Lista de Certificados
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: Para atribuir um certificado, selecione o certificado no repositório de certificado local. Clique em Avançar para continuar.
ms.openlocfilehash: 268d2215aa0a56bc8c86243d99b345831b8d42d1
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2018
---
# <a name="certificate-list"></a>Lista de Certificados
 
Para atribuir um certificado, selecione o certificado no repositório de certificado local. Clique em **Avançar** para continuar.
  
O certificado ou certificados disponíveis para seleção no painel **Selecionar um certificado no Armazenamento local de certificados** são certificados válidos que podem ser atribuídos ao uso do certificado necessário. É possível confirmar se o certificado selecionado é o correto clicando no botão **Exibir Detalhes do Certificado**. Na guia **Detalhes**, é possível exibir o nome da entidade e os nomes de entidade alternativos designados como configurados no certificado.
  
> [!IMPORTANT]
> É possível que nenhum certificado esteja listado no painel de seleção. Quando isso ocorre, a causa típica é que não há certificado raiz confiável ou certificados intermediários de autoridade de certificação instalados no servidor pretendido para verificar o certificado e, dessa forma, manter a cadeia de confiança criada pelo certificado para a autoridade de certificação. Para resolver esse problema, solicite e importe uma cadeia de certificados, que normalmente inclui o certificado de autoridade de certificação (AC) raiz e quaisquer certificados de AC intermediária e AC emissora. 
  

