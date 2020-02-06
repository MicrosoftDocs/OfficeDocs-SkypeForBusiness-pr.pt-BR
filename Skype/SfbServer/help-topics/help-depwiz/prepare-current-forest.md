---
title: Preparar Floresta Atual
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainForestPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 11f5e359-97eb-45f7-a730-9ddbbaa40b83
description: Para preparar a floresta dos serviços de domínio Active Directory, você deve prorrogar o esquema com êxito, conforme descrito no tópico executando a preparação do esquema e certifique-se de que o esquema tenha sido replicado.
ms.openlocfilehash: d13660eb703a793c1fc59ed422bd0b317986a86b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823525"
---
# <a name="prepare-current-forest"></a>Preparar Floresta Atual

Para preparar a floresta dos serviços de domínio Active Directory, você deve prorrogar o esquema com êxito, conforme descrito no tópico [executando a preparação do esquema](https://technet.microsoft.com/library/067726ae-fd3f-4133-a32f-26d2603ac674.aspx)e certifique-se de que o esquema tenha sido replicado.

Depois de atender a esses pré-requisitos, você pode começar a **Etapa 3: preparar floresta atual**. Para preparar a floresta, faça logon em um computador na raiz da floresta como membro de Admins. do Domínio na raiz da floresta, ou como membro de Administradores de Empresa na floresta que você está preparando.

1. No Assistente de Implantação em **Etapa 3: preparar floresta atual**, clique em **Executar**.

2. Na página **Preparar Floresta**, clique em **Próximo**.

    > [!NOTE]
    > A preparação da floresta permite que você escolha onde colocar os grupos universais para o Skype for Business Server 2015. Escolha um local que atenda aos requisitos de sua organização.

3. Na página **Executando Comandos**, procure por **Status da tarefa: Concluída** e clique em **Exibir Log**. Certifique-se de que não haja erros. Revise os avisos a fim de determinar se são esperados e normais para sua infraestrutura.

4. Na coluna **Action** do log, expanda **Forest prep**, procure um ** \<\> ** resultado de execução de sucesso no final de cada tarefa para verificar se a preparação da floresta foi concluída com êxito, feche o log e clique em **concluir**.

5. Aguarde a conclusão da replicação dos serviços de domínio Active Directory ou force a replicação para todos os controladores de domínio listados no snap-in **sites e serviços do Active Directory** para o controlador de domínio raiz da floresta, antes de executar a preparação do domínio. Force a replicação entre os controladores de domínio em todos os sites do Active Directory para fazer com que a replicação dentro dos sites ocorra em minutos.

    > [!TIP]
    > Se precisar analisar os arquivos de log criados pelo assistente de implantação do Skype for Business Server, você poderá encontrá-los no computador em que o assistente de implantação foi executado, no diretório usuários do usuário dos serviços de domínio Active Directory que executou a etapa. Por exemplo, se o usuário tiver entrado como administrador do domínio no domínio Contoso.net, os arquivos de log serão localizados em: C:\Users\Administrator.Contoso\AppData\Local\Temp


