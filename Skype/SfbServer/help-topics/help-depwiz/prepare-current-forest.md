---
title: Preparar Floresta Atual
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Para preparar a floresta dos Serviços de Domínio do Active Directory, você deve estender com êxito o esquema, conforme descrito no tópico Running Schema Preparation, e certificar-se de que o esquema foi replicado.
ms.openlocfilehash: b73be89b857e933f9e461371971eff2c247a39b2
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60761019"
---
# <a name="prepare-current-forest"></a>Preparar Floresta Atual

Para preparar a floresta dos Serviços de Domínio do Active Directory, você deve estender com êxito o esquema, conforme descrito no tópico [Running Schema Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-preparing-the-active-directory-schema), e certificar-se de que o esquema foi replicado.

Depois de atender a esses pré-requisitos, você pode começar a **Etapa 3: preparar a floresta atual**. Para preparar a floresta, faça logon em um computador na raiz da floresta como membro de Admins. do Domínio na raiz da floresta, ou como membro de Administradores de Empresa na floresta que você está preparando.

1. No Assistente de Implantação em **Etapa 3: preparar a floresta atual**, clique em **Executar**.

2. Na página **Preparar Floresta**, clique em **Próximo**.

    > [!NOTE]
    > A Preparação da Floresta permite que você escolha onde colocar os Grupos Universais para Skype for Business Server 2015. Escolha um local que atenda aos requisitos de sua organização.

3. Na página **Executando Comandos**, procure por **Status da tarefa: concluída** e clique em **Exibir Log**. Certifique-se de que não haja erros. Revise os avisos a fim de determinar se são esperados e normais para sua infraestrutura.

4. Na coluna **Ação** no log, expanda **Forest Prep**, procure um Resultado de Execução no final de cada tarefa para verificar se a preparação da floresta foi concluída com êxito, feche o log e clique em **\<Success\>** **Concluir**.

5. Aguarde a conclusão da replicação dos Serviços de Domínio do **Active Directory** ou force a replicação a todos os controladores de domínio listados no snap-in Sites e Serviços do Active Directory para o controlador de domínio raiz da floresta, antes de executar a preparação do domínio. Force a replicação entre os controladores de domínio em todos os sites do Active Directory para que a replicação nos sites ocorra dentro de alguns minutos.

    > [!TIP]
    > Se você precisar revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, poderá encontrá-los no computador onde o Assistente de Implantação foi executado, no diretório Usuários do usuário dos Serviços de Domínio active Directory que executaram a etapa. Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp