---
title: Configurar políticas de arquivamento para Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Resumo: leia este tópico para saber como configurar políticas de arquivamento iniciais para Skype for Business Server usuários.'
ms.openlocfilehash: 6e50f40aa91a26af8833ec7f330b14a9354d6b8b
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399425"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configurar políticas de arquivamento para Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar políticas de arquivamento iniciais para Skype for Business Server usuários.
  
Em Skype for Business Server, você usa políticas para habilitar e desabilitar o arquivamento para comunicações internas e comunicações externas para usuários que estão no Skype for Business Server. Isso inclui:
  
- Uma política global criada por padrão quando você implanta Skype for Business Server
    
- Políticas opcionais no nível do site que especificam como o arquivamento é implementado para um site específico
    
- Políticas opcionais no nível do usuário que especificam como o arquivamento é implementado para usuários específicos
    
Inicialmente, você configura políticas de arquivamento ao implantar o arquivamento, mas pode alterar, adicionar e excluir políticas após a implantação. No Skype for Business Server Painel de Controle, você pode usar a página Política  de Arquivamento do grupo Arquivamento e Monitoramento  para gerenciar políticas nos níveis global, de site e de usuário.
  
> [!NOTE]
> Para controlar a implementação do arquivamento, você deve especificar opções, como se arquivar IM ou conferência, o uso do modo crítico e opções de purgação. Por padrão, nenhuma opção está habilitada na configuração de arquivamento global ou em qualquer configuração de arquivamento de site ou pool. Você deve especificar todas as opções apropriadas antes de habilcar o arquivamento para comunicações internas ou externas. Para obter detalhes, consulte [Configure archiving options for Skype for Business Server](configure-archiving-options.md). 
  
> [!NOTE]
> Se você habilitar Exchange integração do Microsoft Exchange para sua implantação, as políticas de Exchange In-Place Detiver controlarão se o arquivamento está habilitado para os usuários que estão no Exchange e têm suas caixas de correio colocadas em In-Place Hold. 
  
Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md). Para obter detalhes sobre como gerenciar políticas após a implantação, consulte [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Política global

Quando você implanta seus Servidores Front-End, Skype for Business Server cria uma política global para arquivamento. Por padrão, o arquivamento está desabilitado na política global. A política global controla se o arquivamento está habilitado para comunicações internas e externas para toda a sua implantação, a menos que você configurar políticas de site ou usuário, que substituem a política global ou se você usa a integração do Microsoft Exchange para alguns ou todos os seus usuários. Se você usar a integração do Microsoft Exchange, a política global não se aplicará a quaisquer usuários que estão no Exchange e que tenham as caixas de correio colocadas em In-Place Hold.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurar a política global para arquivamento para Skype for Business Server de arquivamento

1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.
    
4. Na página **Política de Arquivamento**, clique em **Global**, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.
    
5. Em **Editar Política de Arquivamento - Global**, faça o seguinte:
    
   - Em **Nome**, se não desejar usar o nome padrão de global, especifique um novo nome para a política global. 
    
   - Em **Descrição**, forneça informações sobre o que é a política (por exemplo, política global  *para divisionName*  .
    
   - Para controlar o arquivamento de comunicações internas para todos os sites e usuários que não estivem sendo controlados especificamente por meio de uma política de site ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
   - Para controlar o arquivamento de comunicações externas para todos os sites e usuários que não estivem sendo controlados especificamente por meio de uma política de site ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.
    
6. Clique em **Confirmar**.
    
## <a name="site-policies"></a>Políticas de site

Você pode habilitar ou desabilitar o arquivamento para sites específicos criando uma política de arquivamento para cada um desses sites. Uma política de site substitui a política global, mas as políticas de usuário substituem as políticas de site. As políticas de arquivamento só se aplicam se você não usar a integração do Microsoft Exchange ou, se você usar a integração do Microsoft Exchange, mas tiver alguns usuários que não estão no Exchange e que tenham suas caixas de correio colocadas em In-Place Hold.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Criar uma política de arquivamento para um site

1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle.
    
3. Na barra de navegação esquerda, clique em **Monitoramento e Arquivamento** e em **Política de Arquivamento**.
    
    Para obter detalhes sobre como as políticas de arquivamento funcionam, incluindo a hierarquia para políticas globais, de site e de usuário, consulte [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Clique em **Novo** e, em seguida, em **Política de site**.
    
5. Em **Selecionar um site**, clique no site ao qual a política deve ser aplicada.
    
6. Em **Nova Política de Arquivamento**, faça o seguinte:
    
   - Em **Nome**, especifique o nome da política de site. 
    
   - Em **Descrição**, forneça informações sobre o que é a política de site (por exemplo, política de site para Redmond).
    
   - Para controlar o arquivamento de comunicações internas para o site especificado, selecione ou desempure a caixa de seleção **Arquivar comunicações** internas.
    
   - Para controlar o arquivamento de comunicações externas para o site especificado, selecione ou desempure a caixa de seleção **Arquivar comunicações externas** .
    
7. Clique em **Confirmar**.
    
## <a name="user-policies"></a>Políticas de usuário

Você pode habilitar ou desabilitar o arquivamento para usuários específicos criando e configurando uma política de arquivamento para usuários e aplicando a política a usuários ou grupos de usuários específicos. As políticas de usuário substituem qualquer política global ou locais. As políticas de arquivamento só se aplicam se você não usar a integração do Microsoft Exchange ou, se você usar a integração do Microsoft Exchange, mas tiver alguns usuários que não estão no Exchange e que tenham suas caixas de correio colocadas em In-Place Hold.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurar uma política de arquivamento para usuários que estão no Skype for Business Server

1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Monitoração e Arquivamento** e em **Política de Arquivamento**.
    
4. Clique em **Novo** e em **Política do usuário**.
    
5. Em **Nova Política de Arquivamento**, faça o seguinte:
    
   - Em **Nome**, especifique o nome da política de usuário. 
    
   - Em **Descrição**, forneça informações sobre a política de usuário (por exemplo, política de usuário do departamento jurídico).
    
   - Para controlar o arquivamento das comunicações internas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
   - Para controlar o arquivamento das comunicações externas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.
    
6. Clique em **Confirmar**.
    
Uma política de usuário aplica-se somente aos usuários aos quais você a atribui.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Aplicar uma Skype for Business Server de arquivamento a um usuário

1. A partir da conta do usuário que foi atribuída à função CsArchivingAdministrator ou CsAdministrator, faça o logon em qualquer computador na sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o painel Skype for Business Server Controle. 
    
3. Na barra de navegação esquerda, clique em **Usuários** e pesquise a conta de usuário que deseja configurar.
    
4. Na tabela que lista os resultados da pesquisa, clique na conta do usuário, em **Editar** e em **Exibir detalhes**.
    
5. Em **Editar Skype for Business Server usuário** em **Política de** Arquivamento, selecione a política de usuário de arquivamento que você deseja aplicar.
    
    > [!NOTE]
    > As **\<Automatic\>** configurações aplicam as configurações de instalação padrão do servidor. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    

