---
title: Lista de Certificados
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertList
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: aaa6b123-b8cd-4b22-846b-8e02beb428b9
description: Para atribuir um certificado, selecione um certificado no armazenamento de certificados local. Clique em Avançar para continuar.
ms.openlocfilehash: 0f7f6b3fc0801a71f8390f82396c2b4711d4295e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60764289"
---
# <a name="certificate-list"></a>Lista de Certificados
 
Para atribuir um certificado, selecione um certificado no armazenamento de certificados local. Clique em **Avançar** para continuar.
  
O certificado ou certificados disponíveis para seleção no painel **Selecionar um certificado no Armazenamento local de certificados** são certificados válidos que podem ser atribuídos ao uso do certificado necessário. É possível confirmar se o certificado selecionado é o correto clicando no botão **Exibir Detalhes do Certificado**. Na guia **Detalhes**, é possível exibir o nome da entidade e os nomes de entidade alternativos designados como configurados no certificado.
  
> [!IMPORTANT]
> É possível que nenhum certificado esteja listado no painel de seleção. Quando isso ocorre, a causa típica é que não há certificado raiz confiável ou certificados de autoridade de certificação intermediárias instalados no servidor pretendido para verificar o certificado e, dessa forma, manter a cadeia de confiança criada pelo certificado para a autoridade de certificação. Para resolver esse problema, solicite e importe uma cadeia de certificados, que normalmente inclui o certificado de autoridade de certificação raiz (CA) e quaisquer certificados CA intermediários e certificados CA emissores. 
  

