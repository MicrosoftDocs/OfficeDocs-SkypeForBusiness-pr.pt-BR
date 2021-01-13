---
title: Verificar a topologia no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumo: Saiba como verificar se a topologia do Skype for Business Server e os servidores do Active Directory estão funcionando conforme o esperado. Baixe uma avaliação gratuita do Skype for Business Server no Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: 0c2307f3ad0416a7175d92a1440744dbda9b31d3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833831"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Verificar a topologia no Skype for Business Server
 
**Resumo:** Saiba como verificar se a topologia do Skype for Business Server e os servidores do Active Directory estão funcionando conforme o esperado. Baixe uma avaliação gratuita do Skype for Business Server no Centro [de Avaliação da Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Depois de publicar a topologia e instalar os componentes do sistema do Skype for Business Server em cada um dos servidores da topologia, você estará pronto para verificar se a topologia está funcionando conforme o esperado. Isso inclui verificar se a configuração foi propagada para todos os servidores do Active Directory para que o domínio inteiro saiba que o Skype for Business está disponível no domínio. Você pode realizar as etapas 1 a 5 em qualquer ordem. No entanto, você deve realizar as etapas 6, 7 e 8 na ordem e após as etapas de 1 a 5, conforme descrito no diagrama. A verificação da topologia é a etapa 8 de 8.
  
![Diagrama de visão geral.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Testar a implantação do pool de Front-End

A etapa final é testar o pool de Front-End e confirmar se os clientes do Skype for Business podem se comunicar entre si. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Adicionar usuários e verificar a conectividade do cliente

1. Use Computadores e Usuários do Active Directory para adicionar o objeto de usuário do Active Directory da função de administrador para a implantação do Skype for Business Server (na qual o Painel de Controle do Skype for Business Server está instalado) ao grupo **CSAdministrator.**
    
    > [!IMPORTANT]
    > Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, receberá um erro ao abrir o Painel de Controle do Skype for Business Server que diz " Não autorizado: o acesso é negado devido a uma falha de autorização de controle de acesso baseado em função (RBAC)." 
  
2. Se o objeto de usuário estiver conectado no momento, saia e faça logon novamente para registrar a nova atribuição de grupo.
    
    > [!NOTE]
    > A conta de usuário não pode ser o administrador local de nenhum servidor que executa o Skype for Business Server. 
  
3. Use a conta administrativa para fazer logon no computador onde o Painel de Controle do Skype for Business Server está instalado.
    
4. Inicie o Painel de Controle do Skype for Business Server e forneça credenciais, se solicitado. O Painel de Controle do Skype for Business Server exibe informações de implantação.
    
5. Na barra de navegação esquerda, clique em **Topologia** e confirme se o status do serviço mostra um computador com uma seta verde e se uma marca de seleção verde para o status de replicação está ao lado de cada função do Skype for Business Server que foi implantada e online. 
    
6. Na barra de navegação esquerda, clique **em Usuários** e em **Habilitar usuários.** 
    
7. Na página **Novo Usuário do Skype for Business Server,** clique em **Adicionar.**
    
8. Para definir parâmetros de pesquisa para os objetos que você deseja encontrar, na página Selecionar do **Active Directory,** você pode selecionar Pesquisar e, opcionalmente, clicar em **Adicionar Filtro.**  Você também pode selecionar **a pesquisa LDAP** e inserir uma expressão LDAP para filtrar ou limitar os objetos que serão retornados. Depois de decidir suas opções de Pesquisa, clique em **Encontrar.**
    
9. No painel Resultados da Pesquisa, selecione os usuários que você deseja adicionar e clique em **OK.**
    
10. Na página **Novo Usuário do Skype for Business Server,** os usuários selecionados estão na **exibição Usuários.** Na lista **Atribuir usuários a um pool,** selecione o servidor onde os usuários devem residir.
    
    A seguir está uma lista de opções que você pode usar para configurar os objetos.
    
    - **Gerar o URI do SIP do usuário**
    
    - **Telefonia**
    
    - **URI da linha**
    
    - **Política de conferência**
    
    - **Política de versão do cliente**
    
    - **Política de PIN**
    
    - **Política de acesso externo**
    
    - **Política de arquivamento**
    
    - **Política de local**
    
    - **Política de cliente**
    
    Para testar a funcionalidade básica, selecione a opção de sua preferência para a configuração Gerar **URI do SIP** do usuário (as outras opções na configuração usam configurações padrão) e clique em Habilitar, conforme mostrado na figura.
    
     ![Habilitar usuários no Painel de Controle.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. É exibida uma página de resumo que  mostra uma marca de seleção na coluna Habilitado para indicar que os usuários estão configurados. A **coluna endereço SIP** exibe o endereço necessário para a configuração de entrada do usuário.
    
     ![Usuários adicionados ao Painel de Controle do Skype for Business Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Faça logoff de um usuário em um computador que ingressou no domínio e outro usuário em outro computador no domínio.
    
13. Instale o cliente Skype for Business em cada um dos dois computadores cliente e verifique se ambos os usuários podem entrar no Skype for Business Server e podem enviar mensagens instantâneas entre si.
    

