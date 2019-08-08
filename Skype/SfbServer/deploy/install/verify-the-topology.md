---
title: Verificar a topologia no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/14/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumo: saiba como verificar se a topologia do Skype for Business Server e os servidores do Active Directory estão funcionando conforme esperado. Baixe um teste grátis do Skype for Business Server no centro de avaliação da Microsoft em https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server:.'
ms.openlocfilehash: 6c7d7a67cab2cbd383ee26eb64f478985bcc4b27
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245233"
---
# <a name="verify-the-topology-in-skype-for-business-server"></a>Verificar a topologia no Skype for Business Server
 
**Resumo:** Saiba como verificar se a topologia do Skype for Business Server e os servidores do Active Directory estão funcionando conforme esperado. Baixe um teste grátis do Skype for Business Server no [centro de avaliação da Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Após a publicação da topologia e dos componentes do sistema do Skype for Business Server instalados em cada um dos servidores na topologia, você estará pronto para verificar se a topologia está funcionando conforme o esperado. Isso inclui verificar se a configuração foi propagada para todos os servidores do Active Directory para que todo o domínio saiba que o Skype for Business está disponível no domínio. Você pode executar os passos 1 a 5 em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama. A verificação da topologia é a etapa 8 de 8.
  
![Diagrama de visão geral.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Teste a implantação do pool de Front-Ends

A etapa final é testar o pool de front-ends e confirmar se os clientes do Skype for Business podem se comunicar uns com os outros. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Adicione usuários e verifique a conectividade do cliente

1. Use computadores e usuários do Active Directory para adicionar o objeto de usuário do Active Directory da função Administrador para a implantação do Skype for Business Server (no qual o painel de controle do Skype for Business Server está instalado) no grupo **CSAdministrator** .
    
    > [!IMPORTANT]
    > Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, receberá um erro ao abrir o painel de controle do Skype for Business Server, que lê "não autorizado: o acesso é negado devido a uma falha de autorização de controle de acesso baseado em função (RBAC) ." 
  
2. Se o objeto do usuário está conectado atualmente, desconecte e conecte-se novamente para registrar a nova atribuição de grupo.
    
    > [!NOTE]
    > A conta de usuário não pode ser o administrador local de qualquer servidor que esteja executando o Skype for Business Server. 
  
3. Use a conta administrativa para fazer logon no computador em que o painel de controle do Skype for Business Server está instalado.
    
4. Inicie o painel de controle do Skype for Business Server e forneça as credenciais, se for solicitado. O painel de controle do Skype for Business Server exibe informações de implantação.
    
5. Na barra de navegação à esquerda, clique em **topologia**e, em seguida, confirme se o status do serviço mostra um computador com uma seta verde e se uma marca de seleção verde para o status de replicação está ao lado de cada função do servidor do Skype for Business que foi implantada e colocada online. 
    
6. Na barra de navegação esquerda, clique em **Usuários** e em **Habilitar usuários**. 
    
7. Na página **novo usuário do Skype for Business Server** , clique em **Adicionar**.
    
8. Para definir os parâmetros de pesquisa para os objetos que deseja localizar, na página **Selecionar do Active Directory**, você pode selecionar **Pesquisa** e, opcionalmente, clique em **Adicionar filtro**. Também é possível selecionar **Pesquisa LDAP** e inserir uma expressão LDAP para filtrar ou limitar os objetos que serão retornados. Após decidir suas opções de pesquisa, clique em **Localizar**.
    
9. No painel de resultados da pesquisa, selecione os usuários que você quer adicionar e clique em **OK**.
    
10. Na página **novo usuário do Skype for Business Server** , os usuários selecionados estão na exibição **usuários** . In the **Assign users to a pool** list, select the server where the users should reside.
    
    A seguinte lista inclui as opções que você pode usar para configurar os objetos.
    
    - **Gerar URI SIP do usuário**
    
    - **Telefonia**
    
    - **URI de linha**
    
    - **Política de conferência**
    
    - **Política de versão do cliente**
    
    - **Política de PIN**
    
    - **Política de acesso externo**
    
    - **Política de arquivamento**
    
    - **Política local**
    
    - **Política de cliente**
    
    Para testar a funcionalidade básica, selecione a opção que você prefere para a configuração **gerar URI SIP do usuário** (as outras opções na configuração usar configurações padrão) e, em seguida, clique em **habilitar**, conforme mostrado na figura.
    
     ![Habilitar usuários no painel de controle.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Será exibida uma página de resumo mostrando uma marca de verificação na coluna **Habilitado** para indicar que os objetos agora estão configurados. A coluna **Endereço SIP** exibe o endereço necessário para a configuração de login do usuário.
    
     ![Usuários adicionados ao painel de controle do Skype for Business Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Faça o logon de um usuário em um computador que tenha ingressado no domínio e outro usuário em outro computador no domínio.
    
13. Instale o Skype for Business cliente em cada um dos dois computadores cliente e verifique se os dois usuários podem entrar no Skype for Business Server e enviar mensagens de chat para os outros.
    

