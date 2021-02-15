---
title: Preparar Floresta Atual
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
ROBOTS: NOINDEX, NOFOLLOW
description: Para preparar a floresta dos Serviços de Domínio Active Directory, você deve estender com êxito o esquema, conforme descrito no tópico Running Schema Preparation, e certificar-se de que o esquema tenha replicado.
ms.openlocfilehash: 4881cb85134fef81cd741d834f319a76d4028e59
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833821"
---
# <a name="prepare-current-forest"></a>Preparar Floresta Atual

Para preparar a floresta dos Serviços de Domínio Active Directory, você deve estender com êxito o esquema, conforme descrito no tópico [Running Schema Preparation](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx), e certificar-se de que o esquema tenha replicado.

Depois de atender a esses pré-requisitos, você pode começar a **Etapa 3: preparar a floresta atual**. Para preparar a floresta, faça logon em um computador na raiz da floresta como membro de Admins. do Domínio na raiz da floresta, ou como membro de Administradores de Empresa na floresta que você está preparando.

1. No Assistente de Implantação em **Etapa 3: preparar a floresta atual**, clique em **Executar**.

2. Na página **Preparar Floresta**, clique em **Próximo**.

    > [!NOTE]
    > A Preparação da Floresta permite que você escolha onde colocar os Grupos Universais do Skype for Business Server. Escolha um local que atenda aos requisitos de sua organização.

3. Na página **Executando Comandos**, procure por **Status da tarefa: concluída** e clique em **Exibir Log**. Certifique-se de que não haja erros. Revise os avisos a fim de determinar se são esperados e normais para sua infraestrutura.

4. Under the **Action** column in the log, expand **Forest Prep**, look for a Execution Result at the end of each task to verify that forest preparation **\<Success\>** completed successfully, close the log, and then click **Finish**.

5. Aguarde a conclusão da replicação dos Serviços de Domínio Active Directory ou force a replicação em todos os controladores de domínio listados no snap-in Sites e Serviços do **Active Directory** para o controlador de domínio raiz da floresta, antes de executar a preparação do domínio. Force a replicação entre os controladores de domínio em todos os sites do Active Directory para que a replicação nos sites ocorra dentro de alguns minutos.

    > [!TIP]
    > Se precisar revisar os arquivos de log criados pelo Assistente de Implantação do Skype for Business Server, você poderá encontrá-los no computador onde o Assistente de Implantação foi executado, no diretório Usuários do usuário dos Serviços de Domínio Active Directory que executaram a etapa. Por exemplo, se o usuário fez logon como administrador de domínio no domínio Contoso.net, os arquivos de log estão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp


