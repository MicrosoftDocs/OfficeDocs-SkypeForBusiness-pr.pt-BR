---
title: Verifique a topologia em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumo: Saiba como verificar se os servidores Skype for Business Server topologia e Active Directory estão funcionando conforme o esperado. Baixe uma avaliação gratuita de Skype for Business Server do Centro de Avaliação da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server .'
ms.openlocfilehash: ba098dd808fec192cc944ed3796d5e11b0d8af31
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753234"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Verifique a topologia em Skype for Business Server
 
**Resumo:** Saiba como verificar se a topologia Skype for Business Server e os servidores do Active Directory estão funcionando conforme o esperado. Baixe uma avaliação gratuita de Skype for Business Server do Centro [de Avaliação da Microsoft.](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)
  
Depois de publicar a topologia e os Skype for Business Server do sistema instalados em cada um dos servidores na topologia, você estará pronto para verificar se a topologia está funcionando conforme esperado. Isso inclui verificar se a configuração foi propagada para todos os servidores do Active Directory para que todo o domínio saiba Skype for Business está disponível no domínio. Você pode realizar as etapas 1 a 5 em qualquer ordem. No entanto, você deve realizar as etapas 6, 7 e 8 em ordem e após as etapas 1 a 5, conforme descrito no diagrama. Verificar a topologia é a etapa 8 de 8.
  
![Diagrama de visão geral.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Testar a implantação do pool de Front-End

A etapa final é testar o pool de Front-End e confirmar se Skype for Business clientes podem se comunicar uns com os outros. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Adicionar usuários e verificar a conectividade do cliente

1. Use Computadores e Usuários do Active Directory para adicionar o objeto de usuário do Active Directory da função de administrador para Skype for Business Server implantação do Skype for Business Server (no qual o Painel de Controle do Skype for Business Server está instalado) ao grupo **CSAdministrator.**
    
    > [!IMPORTANT]
    > Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, receberá um erro ao abrir o Painel de Controle do Skype for Business Server que diz: "Não autorizado: o acesso é negado devido a uma falha de autorização de controle de acesso baseado em função (RBAC)." 
  
2. Se o objeto de usuário estiver conectado no momento, saia e faça logon novamente para registrar a nova atribuição de grupo.
    
    > [!NOTE]
    > A conta de usuário não pode ser o administrador local de qualquer servidor que executa Skype for Business Server. 
  
3. Use a conta administrativa para fazer logon no computador onde Skype for Business Server Painel de Controle está instalado.
    
4. Inicie Skype for Business Server Painel de Controle e forneça credenciais, se solicitado. Skype for Business Server Painel de Controle exibe informações de implantação.
    
5. Na barra de navegação esquerda, clique em **Topologia** e, em seguida, confirme se o status do serviço mostra um computador com uma seta verde e que uma marca de verificação verde para o status de replicação está ao lado de cada função Skype for Business Server que foi implantada e trouxe online. 
    
6. Na barra de navegação esquerda, clique em **Usuários** e clique em **Habilitar usuários**. 
    
7. Na página **Novo Skype for Business Server Usuário,** clique em **Adicionar**.
    
8. Para definir parâmetros de pesquisa para os objetos que você deseja encontrar, na página Selecionar do **Active Directory,** você pode selecionar Pesquisar **e,** opcionalmente, clicar em **Adicionar Filtro**. Você também pode selecionar **pesquisa LDAP** e inserir uma expressão LDAP para filtrar ou limitar os objetos que serão retornados. Depois de decidir suas opções de Pesquisa, clique em **Encontrar**.
    
9. No painel Resultados da Pesquisa, selecione os usuários que você deseja adicionar e clique em **OK**.
    
10. Na página **Novo Skype for Business Server Usuário,** os usuários selecionados estão na **exibição Usuários.** Na lista **Atribuir usuários a um pool,** selecione o servidor onde os usuários devem residir.
    
    Veja a seguir uma lista de opções que você pode usar para configurar os objetos.
    
    - **Gerar URI SIP do usuário**
    
    - **Telefonia**
    
    - **URI de linha**
    
    - **Política de conferência**
    
    - **Política de versão do cliente**
    
    - **Política de PIN**
    
    - **Política de acesso externo**
    
    - **Política de arquivamento**
    
    - **Política de local**
    
    - **Política de cliente**
    
    Para testar a funcionalidade básica, selecione a opção que você prefere para a configuração Gerar **URI SIP** do usuário (as outras opções na configuração usam configurações padrão) e clique em Habilitar **,** conforme mostrado na figura.
    
     ![Habilitar usuários no Painel de Controle.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Uma página de resumo é exibida que mostra uma marca de verificação na coluna **Habilitado** para indicar que os usuários estão configurados. A **coluna endereço SIP** exibe o endereço necessário para a configuração de entrada do usuário.
    
     ![Os usuários adicionados Skype for Business Server Painel de Controle.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Faça logoff de um usuário em um computador que está ingressado no domínio e outro usuário em outro computador no domínio.
    
13. Instale Skype for Business cliente em cada um dos dois computadores clientes e verifique se ambos os usuários podem entrar no Skype for Business Server e podem enviar mensagens instantâneas uns para os outros.
    

