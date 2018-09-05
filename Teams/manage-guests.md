---
title: Gerenciamento do acesso de convidados no Microsoft Teams
author: LolaJacobsen
ms.author: rramesan
manager: serdars
ms.date: 10/20/17
ms.topic: article
ms.service: msteams
ms.reviewer: rramesan
description: Os administradores de TI podem adicionar convidados em nível de locatário, definir e gerenciar políticas e permissões de usuários convidados, determinar quais usuários podem convidar convidados e extrair relatórios sobre a atividade do usuário convidado.
appliesto:
- Microsoft Teams
ms.openlocfilehash: bc06626f745eec4106e65da206123fa68b4e208c
ms.sourcegitcommit: 39516662ee3eefe2fb86735c5bae97b3fb32b7ab
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/05/2018
ms.locfileid: "23834907"
---
<a name="manage-guest-access-in-microsoft-teams"></a>Gerenciamento do acesso de convidados no Microsoft Teams
======================================

**Convidado** é um tipo de licença de usuário/na Microsoft Teams que está incluído com todas as inscrições de educação do Office 365, Office 365 Enterprise e Business Premium do Office 365. Não é necessária nenhuma licença adicional do Office 365. O acesso de convidados no Teams é uma configuração em nível de locatário e está desabilitado por padrão. Para obter detalhes sobre como habilitar o acesso de convidado, consulte [Ativar ou desativar o acesso de convidado para equipes da Microsoft](set-up-guests.md).

Depois que o tipo de licença de **usuário/Convidado** está ativado, você pode definir configurações para convidados por meio dos controles descritas na [dos [recursos de gerenciar equipes da Microsoft em sua organização do Office 365](enable-features-office-365.md) e gerenciar equipes durante a transição para o novo sistema operacional Microsoft Equipes e Skype para Business Admin Center](manage-teams-skypeforbusiness-admin-center.md).     
    
Os administradores de TI podem adicionar convidados em nível de locatário, definir e gerenciar políticas e permissões de usuários convidados, determinar quais usuários podem convidar convidados e extrair relatórios sobre a atividade do usuário convidado. Esses controles estão disponíveis no centro de administração do Office 365. O conteúdo e as atividades dos usuários convidados estão sob a mesma proteção de conformidade e auditoria que o restante do Office 365.

Os proprietários de equipe podem convidar novos convidados e adicionar usuários existentes do diretório convidado a suas equipes. Além disso, os proprietários de equipe podem definir capacidades relacionadas à canal para convidados por meio de **gerenciar equipes** > **permissões de convidado**, incluindo permitir que os convidados criar, atualizar e excluir canais, conforme mostrado na seguinte imagem:

![Configurações de permissões de convidado em equipes.](media/view-guests-guest-permissions.png)
  

Além disso, você pode usar o portal do Azure Active Directory para gerenciar os convidados e o seu acesso aos recursos do Office 365 e do Teams. O acesso de convidados das equipes faz uso dos recursos de colaboração entre empresas (B2B) do Azure Active Directory como a infraestrutura subjacente para armazenar informações de princípios de segurança, como propriedades de identidade, assinaturas e configurações de autenticação multifator. Para saber mais sobre o Azure Active Directory B2B, consulte [O que é a colaboração do Azure AD B2B?](https://go.microsoft.com/fwlink/p/?linkid=853011) e [Perguntas frequentes de colaboração do Azure Active Directory B2B](https://go.microsoft.com/fwlink/p/?linkid=853020).
> [!NOTE]
> Microsoft Teams sempre respeita configurações externas do Azure Active Directory para permitir ou impedir a adição do usuário convidado para o inquilino. Para obter mais detalhes, consulte [autorizar o acesso de convidado em equipes da Microsoft](Teams-dependencies.md).
  
