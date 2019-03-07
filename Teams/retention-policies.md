---
title: Políticas de retenção no Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Saiba mais sobre como as políticas de retenção e como gerenciá-los em equipes.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4d07629f41a54dcab1995f2aef2d7536479be25d
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464552"
---
# <a name="retention-policies-in-microsoft-teams"></a>Políticas de retenção no Microsoft Teams

As equipes conversas são persistentes e retido para sempre por padrão. Com a introdução das políticas de retenção, admins pode configurar políticas de retenção (preservação e exclusão) no & a segurança Centro de conformidade para mensagens de chat e canal de equipes. Isso ajuda as organizações a reter dados para fins de conformidade (isto é, a diretiva de preservação) por um período específico ou se livrar de dados (ou seja, a política de exclusão), se ele é considerado um passivo após um período específico. Políticas de retenção de equipes Certifique-se de que, quando você exclui dados, ele será removido de todos os locais de armazenamento de dados permanentes no serviço equipes. 

Para gerenciar políticas de retenção de equipes, use as configurações e os cmdlets no & de segurança do Office 365 Centro de conformidade em um **Governança dados** > **retenção**.

Políticas de retenção de equipes têm suporte para: 
    
- Preservação: Manter dados de equipes por um período especificado e, em seguida, eu não fizer nada
- Preservação e, em seguida, excluir: manter dados de equipes por um período especificado e excluir
- Exclusão: Excluir dados de equipes após um período especificado

Políticas de retenção de equipes ainda não suportam:

- Políticas de retenção avançada não se aplicam ao chat de equipes e locais de mensagem de canal de equipes
- Duração de menos de 30 dias

Administradores podem configurar políticas de retenção separados para mensagens de canal de equipes e chats privadas de equipes (1:1 ou 1: muitos chats). Em muitos casos, as organizações considerar os dados de bate-papo privado como mais de uma obrigação de mensagens de canal, que geralmente são mais conversas relacionados ao projeto. Configurar essas diretivas de segurança & Centro de conformidade, **governança de dados** > **retenção**. Ative **equipes mensagens de canal** e **equipes de bate-papos** e, em seguida, definir políticas de retenção desses locais (também é mostradas no diagrama a seguir). 

Quando você ativa **as mensagens de canal de equipes**, você pode especificar as equipes ao qual esta política será aplicada. Por exemplo, para as equipes X, Y e Z, o administrador pode definir as políticas de exclusão por 1 ano (selecionando essas equipes individualmente) e aplicar uma política de exclusão de 3 anos para o restante das equipes. 

Você pode fazer a mesma coisa por **equipes chats** selecionando usuários específicos e aplicar políticas de retenção exclusivo. 

![Diagrama do fluxo de trabalho dos dados do Microsoft Teams para o Exchange e o SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Os locais de mensagem do canal de equipes e os locais de chats de equipes apenas endereços as conversas de equipes armazenadas em caixas de correio Exchange Online (caixas de correio grupo e usuário). As mensagens são excluídas de todos os locais de armazenamento relevantes, notadamente as caixas de correio, substrate e serviço de bate-papo. 
> 
> Para gerenciar políticas de retenção para arquivos de equipes, que são armazenados no OneDrive para negócios e do SharePoint, use suas políticas de retenção.

Por design, as políticas de exclusão para arquivos de equipes são configuradas por meio do SharePoint Online e OneDrive para locais de negócios. Como resultado, é possível que uma política foi possível excluir um arquivo referenciado em uma mensagem de bate-papo ou canal de equipes antes que essas mensagens são excluídas. Nesse caso, o arquivo ainda serão exibidas na mensagem de equipes, mas se você clicar no arquivo, você receberá um erro "Arquivo não encontrado" (Isso também pode acontecer na ausência de uma política, se alguém manualmente exclui um arquivo do SharePoint Online ou do OneDrive for Business).

Para obter informações detalhadas sobre como configurar as políticas de retenção para o Office 365, leia a [Visão geral das políticas de retenção](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 
