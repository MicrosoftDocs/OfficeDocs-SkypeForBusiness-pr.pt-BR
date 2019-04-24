---
title: Configurar políticas de arquivamento do Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Resumo: Leia este tópico para saber como configurar políticas de arquivamento iniciais do Skype para usuários corporativos Server.'
ms.openlocfilehash: 88840d10cbd7a71b32b5079a8600018b97e8b0c3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233241"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a>Configurar políticas de arquivamento do Skype para Business Server
 
**Resumo:** Leia este tópico para saber como configurar políticas de arquivamento iniciais do Skype para usuários corporativos Server.
  
Skype para Business Server, você usa políticas para habilitar e desabilitar o arquivamento de comunicações internas e comunicações externas para usuários hospedados no Skype para Business Server. Isso inclui o seguinte:
  
- Uma política global que é criada por padrão, quando você implanta o Skype para Business Server
    
- Políticas opcionais no nível do local que especificam como o arquivamento é implementado para um local específico
    
- Políticas opcionais de nível de usuário que especificam como o arquivamento é implementado para usuários específicos
    
As políticas de arquivamento são configuradas inicialmente ao implantar o arquivamento, mas você pode alterar, adicionar e excluir políticas após a implantação. No painel de controle do servidor de negócios do Skype, você pode usar a página **Política de arquivamento** do grupo de **arquivamento e monitoramento** para gerenciar políticas no nível global, site e níveis de usuário.
  
> [!NOTE]
> Para controlar a implementação do arquivamento, você deve especificar opções, como se é necessário arquivar IM ou conferências, o uso do modo crítico e as opções de limpeza. Por padrão, nenhuma opção está habilitada na configuração de arquivamento global ou em qualquer configuração de arquivamento de local ou pool. É necessário especificar todas as opções apropriadas antes de habilitar o arquivamento para comunicações internas ou externas. Para obter detalhes, consulte [Configurar opções de arquivamento para Skype para Business Server](configure-archiving-options.md). 
  
> [!NOTE]
> Se você habilitar a integração do Microsoft Exchange para sua implantação, o controle de políticas de retenção de In-loco do Exchange se o arquivamento estiver habilitado para os usuários hospedados no Exchange e tem colocado de suas caixas de correio em bloqueio In-loco. 
  
Para obter detalhes sobre políticas de arquivamento como funcionam, incluindo a hierarquia de globais, de site e políticas de usuário, consulte [Planejar para arquivamento no Skype para Business Server](../../plan-your-deployment/archiving/archiving.md). Para obter detalhes sobre como gerenciar políticas após a implantação, consulte [Gerenciar políticas de arquivamento no Skype para Business Server](../../manage/archiving/policies.md).
  
## <a name="global-policy"></a>Política global

Quando você implanta seus servidores Front-End, Skype para Business Server cria uma política global para arquivamento. Por padrão, o arquivamento está desabilitado na política global. A política global controla se o arquivamento estiver habilitado para comunicações internas e externas para sua implantação inteira, a menos que você configure políticas de site ou de usuário, que substituem a política global, ou se você usar a integração do Microsoft Exchange para alguns ou todos seus usuários. Se você usar a integração do Microsoft Exchange, a política global não se aplica a todos os usuários hospedados no Exchange e têm as caixas de correio colocadas em retenção In-loco.
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a>Configurar a política global para arquivamento para Skype para bancos de dados de arquivamento do servidor de negócios

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.
    
4. Na página **Política de Arquivamento**, clique em **Global**, clique em **Editar** e, em seguida, clique em **Mostrar detalhes**.
    
5. Em **Editar Política de Arquivamento - Global**, faça o seguinte:
    
   - Em **Nome**, se não desejar usar o nome padrão da opção Global, especifique um novo nome para a política global. 
    
   - Em **Descrição**, forneça informações sobre o que é a política (por exemplo, política Global para *divisionName* .
    
   - Para controlar o arquivamento de comunicações internas para todos os locais e usuários que não estivem sendo controlados especificamente por meio de uma política de local ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
   - Para controlar o arquivamento de comunicações externas para todos os locais e usuários que não estivem sendo controlados especificamente por meio de uma política de local ou de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.
    
6. Clique em **Confirmar**.
    
## <a name="site-policies"></a>Políticas de local

É possível habilitar ou desabilitar o arquivamento para locais específicos criando uma política de arquivamento para cada um destes locais. Uma política de local substitui a política global, mas as políticas de usuário substituem as políticas de local. Políticas de arquivamento se aplicam somente se você não usar a integração do Microsoft Exchange ou, se você usar a integração do Microsoft Exchange, mas tem colocado de alguns usuários que não são hospedados no Exchange e têm suas caixas de correio em bloqueio In-loco.
  
### <a name="create-an-archiving-policy-for-a-site"></a>Para criar uma política de arquivamento para um local

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios.
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.
    
    Para obter detalhes sobre políticas de arquivamento como funcionam, incluindo a hierarquia de globais, de site e políticas de usuário, consulte [Planejar para arquivamento no Skype para Business Server](../../plan-your-deployment/archiving/archiving.md).
    
4. Clique em **Nova** e em **Política de local**.
    
5. Em **Selecionar um local**, clique no local ao qual a política deve ser aplicada.
    
6. Em **Nova Política de Arquivamento**, faça o seguinte:
    
   - Em **Nome**, especifique um nome para a política do local. 
    
   - Em **Descrição**, forneça as informações sobre a política de local (por exemplo, a política de local para Redmond).
    
   - Para controlar o arquivamento das comunicações internas do local especificado, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
   - Para controlar o arquivamento das comunicações externas do local especificado, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.
    
7. Clique em **Confirmar**.
    
## <a name="user-policies"></a>Políticas de usuário

É possível habilitar ou desabilitar o arquivamento para usuários específicos criando e configurando uma política de arquivamento para usuários e aplicando a política para usuários ou grupos de usuários específicos. As políticas de usuário substituem qualquer política global ou local. Políticas de arquivamento se aplicam somente se você não usar a integração do Microsoft Exchange ou, se você usar a integração do Microsoft Exchange, mas tem colocado de alguns usuários que não são hospedados no Exchange e têm suas caixas de correio em bloqueio In-loco.
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a>Configurar uma política de arquivamento para usuários hospedados no Skype para Business Server

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação da esquerda, clique em **Monitoramento e Arquivamento**, e depois, clique em **Política de Arquivamento**.
    
4. Clique em **Nova** e em **Política do usuário**.
    
5. Em **Nova Política de Arquivamento**, faça o seguinte:
    
   - Em **Nome**, especifique o nome da política de usuário. 
    
   - Em **Descrição**, forneça informações sobre a política de usuário (por exemplo, política de usuário do departamento jurídico).
    
   - Para controlar o arquivamento das comunicações internas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações internas**.
    
   - Para controlar o arquivamento das comunicações externas para a política de usuário, marque ou desmarque a caixa de seleção **Arquivar comunicações externas**.
    
6. Clique em **Confirmar**.
    
Uma política de usuário aplica-se somente aos usuários aos quais você a atribui.
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a>Aplicar um Skype para Business Server política a um usuário de arquivamento

1. Usando uma conta de usuário atribuída à função CsArchivingAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra uma janela do navegador e insira a URL do administrador para abrir o Skype para painel de controle do servidor de negócios. 
    
3. Na barra de navegação à esquerda, clique em **Usuários** e procure a conta de usuário que deseja configurar.
    
4. Na tabela que lista os resultados da pesquisa, clique em conta de usuário, em **Editar** e em **Mostrar detalhes**.
    
5. Em **Editar Skype para usuário Business Server** , em **política de arquivamento**, selecione a política de usuário de arquivamento que você deseja aplicar.
    
    > [!NOTE]
    > O ** \<automática\> ** configurações se aplicam as configurações de instalação de servidor padrão. Essas configurações são aplicadas automaticamente pelo servidor.
  
6. Clique em **Confirmar**.
    

