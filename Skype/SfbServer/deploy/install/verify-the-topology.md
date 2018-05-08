---
title: Verificar a topologia no Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 7/14/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a4f4bad1-fc59-47ce-a3ea-b1b893769db6
description: 'Resumo: Saiba como verificar o Skype para a topologia de servidor de negócios e os servidores do Active Directory estão funcionando conforme o esperado. Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do centro da Evaluation da Microsoft em: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server.'
ms.openlocfilehash: 93696511ab415d4e3df65e6d2e3c5efcb621c39d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/03/2018
---
# <a name="verify-the-topology-in-skype-for-business-server-2015"></a>Verificar a topologia no Skype for Business Server 2015
 
**Resumo:** Saiba como verificar o Skype para a topologia de servidor de negócios e os servidores do Active Directory estão funcionando conforme o esperado. Baixe uma versão de avaliação gratuita do Skype para negócios 2015 de servidor do [Centro de avaliação do Microsoft](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server).
  
Depois que a topologia publicada e o Skype para componentes do sistema Business Server instalado em cada um dos servidores na topologia, você estará pronto para verificar se a topologia está funcionando conforme o esperado. Isso inclui a opção confirmar que a configuração tenha propagadas check-out para todos os servidores do Active Directory para que o domínio inteiro reconheça que Skype para a empresa está disponível no domínio. As etapas 1 a 5 podem ser executadas em qualquer ordem. No entanto, você deve executar as etapas 6, 7 e 8 nesta ordem, após concluir as etapas 1 a 5, conforme descrito no diagrama. A verificação da topologia é a etapa 8 de 8.
  
![Diagrama de visão geral.](../../media/c8698b53-1282-4978-a9a6-ca3f7a778f60.png)
  
## <a name="test-the-front-end-pool-deployment"></a>Teste a implantação do pool de Front-Ends

A etapa final é testar o pool de Front-End e confirme que o Skype para clientes corporativos pode se comunicar entre si. 
  
### <a name="add-users-and-verify-client-connectivity"></a>Adicione usuários e verifique a conectividade do cliente

1. Use usuários e computadores do Active Directory para adicionar o objeto de usuário do Active Directory da função de administrador para o Skype para implantação de servidor de negócios (no qual Skype para painel de controle do Business Server está instalado) para o grupo **CSAdministrator** .
    
    > [!IMPORTANT]
    > Se você não adicionar os usuários e grupos apropriados ao grupo CsAdministors, você receberá um erro quando você abre o Skype para painel de controle do servidor de negócios que lê, "não autorizado: acesso negado devido a uma falha de autorização do acesso baseado em função RBAC (controle) ." 
  
2. Se o objeto do usuário está conectado atualmente, desconecte e conecte-se novamente para registrar a nova atribuição de grupo.
    
    > [!NOTE]
    > A conta de usuário não pode ser o administrador local de qualquer servidor executando o Skype para Business Server. 
  
3. Use a conta administrativa para fazer logon no computador onde o Skype para painel de controle do Business Server está instalado.
    
4. Inicie o Skype para painel de controle do servidor de negócios e forneça as credenciais, se solicitado. Skype para painel de controle do Business Server exibe informações sobre a implantação.
    
5. Na barra de navegação à esquerda, clique em **topologia**e, em seguida, confirme se o status do serviço mostra um computador com uma seta verde e que uma marca de seleção verde para obter o status de replicação está localizado ao lado de cada Skype para a função de servidor de negócios que tenha sido implantada e colocada on-line. 
    
6. Na barra de navegação esquerda, clique em **Usuários** e em **Habilitar usuários**. 
    
7. Na página **Novo Skype para usuário de servidor de negócios** , clique em **Adicionar**.
    
8. Para definir os parâmetros de pesquisa para os objetos que deseja localizar, na página **Selecionar do Active Directory**, você pode selecionar **Pesquisa** e, opcionalmente, clique em **Adicionar filtro**. Também é possível selecionar **Pesquisa LDAP** e inserir uma expressão LDAP para filtrar ou limitar os objetos que serão retornados. Após decidir suas opções de pesquisa, clique em **Localizar**.
    
9. No painel de resultados da pesquisa, selecione os usuários que você quer adicionar e clique em **OK**.
    
10. Na página **Novo Skype para usuário de servidor de negócios** , os usuários que você selecionou estão na exibição de **usuários** . Na lista **Atribuir usuários a um pool**, selecione o servidor onde os usuários devem ser hospedados.
    
    A seguinte lista inclui as opções que você pode usar para configurar os objetos.
    
    - **Gerar o URI do SIP do usuário**
    
    - **Telefonia**
    
    - **URI de linha**
    
    - **Política de conferência**
    
    - **Política de versão do cliente**
    
    - **Política de PIN**
    
    - **Política de acesso externo**
    
    - **Política de arquivamento**
    
    - **Política local**
    
    - **Política de cliente**
    
    Para testar a funcionalidade básica, selecione a opção que você prefere para que a configuração **URI SIP do usuário Generate** (as outras opções nas configurações padrão de uso de configuração) e clique em **Habilitar**, conforme mostrado na figura.
    
     ![Habilite os usuários no Painel de Controle.](../../media/7ee8717d-9a1f-4864-8f45-71071c88878f.png)
  
11. Será exibida uma página de resumo mostrando uma marca de verificação na coluna **Habilitado** para indicar que os objetos agora estão configurados. A coluna **Endereço SIP** exibe o endereço necessário para a configuração de login do usuário.
    
     ![Usuários adicionados ao Painel de Controle do Skype for Business Server.](../../media/8960548a-8d6d-44c5-bc01-6f9fb11b7588.png)
  
12. Faça o logon de um usuário em um computador que tenha ingressado no domínio e outro usuário em outro computador no domínio.
    
13. Instale o Skype para o cliente de negócios em cada um dos dois computadores cliente e, em seguida, verifique se ambos os usuários podem se conectar ao Skype para Business Server e podem enviar mensagens instantâneas entre si.
    

