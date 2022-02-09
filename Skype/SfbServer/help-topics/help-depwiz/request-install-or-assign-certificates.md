---
title: Solicitar, Instalar ou Atribuir Certificados
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainCerts
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 332ec40f-78be-440a-8c1d-ada6114897db
description: 'Etapa 3: Solicitar, Instalar ou Atribuir Certificados inicia o Assistente de Certificado quando você clica em Executar. Os certificados configurados por meio do assistente se baseiam na definição da topologia do Skype for Business Server 2015 que é configurada e publicada pelo Construtor de Topologias no armazenamento de Gerenciamento Central. Para executar com êxito o Assistente de Certificado para uma autoridade de certificação (CA) online em sua organização, é necessário estar conectado ao computador como usuário membro do grupo de administradores local do computador. Também é necessário ser um Usuário de Domínio autenticado no domínio no qual o computador e a CA existem. O assistente de certificado fornece a capacidade de especificar credenciais alternativas para acessar a AC da sua organização.'
ms.openlocfilehash: b535f1070ce240b63d69c2cceb54f15a9b92a9e8
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401385"
---
# <a name="request-install-or-assign-certificates"></a>Solicitar, Instalar ou Atribuir Certificados
 
 **Etapa 3: Solicitar, Instalar ou Atribuir Certificados** inicia o Assistente de Certificado quando você clica em **Executar**. Os certificados configurados por meio do assistente se baseiam na definição da topologia do Skype for Business Server 2015 que é configurada e publicada pelo Construtor de Topologias no armazenamento de Gerenciamento Central. Para executar com êxito o Assistente de Certificado para uma autoridade de certificação (CA) online em sua organização, é necessário estar conectado ao computador como usuário membro do grupo de administradores local do computador. Também é necessário ser um Usuário de Domínio autenticado no domínio no qual o computador e a CA existem. O assistente de certificado fornece a capacidade de especificar credenciais alternativas para acessar a AC da sua organização.
  
> [!NOTE]
> Também é possível usar o Assistente de Certificado para solicitar e processar as solicitações de certificado offline enviadas a uma CA pública ou outra PKI (infraestrutura de chave pública) offline. Não há associações de grupo específicas, além das necessárias para fazer logon no computador, para gerar uma solicitação offline. Para processar a resposta de CA pública e atribuir o certificado ao computador e função, é necessário estar conectado como membro do grupo local Administradores ou equivalente. 
  

