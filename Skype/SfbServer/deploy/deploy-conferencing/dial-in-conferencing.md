---
title: Configurar a conferência discada no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 38d9f168-80b8-46f2-a1c0-becd84e58e73
description: 'Resumo: Leia este tópico para saber como configurar a conferência discada no Skype for Business Server.'
ms.openlocfilehash: 7c62ef5ec984fe89033aa4813bca9674979c1c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298232"
---
# <a name="configure-dial-in-conferencing-in-skype-for-business-server"></a>Configurar a conferência discada no Skype for Business Server
 
**Resumo:** Leia este tópico para saber como configurar a conferência discada no Skype for Business Server.
  
Depois de criar uma topologia que inclua a carga de trabalho de conferência e a conferência discada selecionada, você deve executar etapas adicionais para configurar a conferência discada. Antes de ler este tópico, certifique-se de ter lido [plano para conferência discada no Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md), [requisitos de hardware e software para conferência no Skype for Business Server](../../plan-your-deployment/conferencing/hardware-and-software-requirements.md), e o [fluxograma de implantação e lista de verificação para conferência discada](deploy-conferencing.md#deployment-flowchart-and-checklist-for-dial-in-conferencing). 
  
Para configurar a conferência discada, você deve executar as seguintes tarefas:
  
- [Configure dial plans](dial-in-conferencing.md#BKMK_ConfigureDialPlans)
    
- [Configure dial-in conferencing regions](dial-in-conferencing.md#BKMK_ConfigureDialInRegions)
    
- [Configure dial-in access numbers](dial-in-conferencing.md#BKMK_ConfigureDialInAccessNumbers)
    
- [Configure conferencing policies](dial-in-conferencing.md#BKMK_ConfigureConferencingPolicies)
    
- [Assign a Line URI to a user account](dial-in-conferencing.md#BKMK_AssignaLineURI)
    
Além disso, você pode executar as seguintes tarefas opcionais. Para obter mais informações sobre essas tarefas opcionais, consulte [gerenciar conferência discada no Skype for Business Server](../../manage/conferencing/dial-in-conferencing.md).
  
- Gerenciar políticas de PIN para conferência discada
    
- Gerenciar mapeamento principal de comandos DTMF
    
- Criar diretórios de conferência
    
- Gerenciar o ingresso na conferência e anúncios de saída
    
- Testar configurações de conferência discada
    
- Enviar e-mail de boas-vindas para os usuários de discagem
    
## <a name="configure-dial-plans"></a>Configure planos de discagem
<a name="BKMK_ConfigureDialPlans"> </a>

Ao implantar a conferência discada, você precisa criar ou modificar um ou mais planos de discagem para o roteamento de números de telefone de acesso de discagem. Você também deve certificar-se de que cada plano de discagem contenha pelo menos uma regra de normalização – uma regra que converte ramais telefônicos em números de telefone completos no formato E. 164. 
  
Os usuários da conferência discada participam de conferências como usuários corporativos autenticados, digitando seu número de identificação pessoal (PIN) e seu número de telefone. Você precisa de uma regra de normalização para converter ramais em números de telefone completos, de forma que os usuários possam ser autenticados ao inserir somente um ramal telefônico.
  
Para configurar planos de discagem para conferência discada:
  
- Independente de implantar o Enterprise Voice, modifique o plano de discagem global para adicionar uma região de conferência discada e para garantir que uma regra de normalização converta seus números de acesso discado de modo preciso. Para obter instruções detalhadas, consulte [criar ou modificar um plano de discagem no Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Se você não implantou o Enterprise Voice, crie planos de discagem para todos os seus números de acesso de conferência discada. Certifique-se de incluir uma região de conferência discada. Para obter instruções detalhadas, consulte [criar ou modificar um plano de discagem no Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
- Se você implantou o Enterprise Voice, modifique os planos de discagem do Enterprise Voice conforme necessário para incluir regiões e usar regras de normalização apropriadas para números de acesso de discagem. Você também pode criar planos de discagem dedicados, usados somente para números de acesso de discagem. Para obter instruções detalhadas, consulte [criar ou modificar um plano de discagem no Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
    
Para obter detalhes sobre como criar regras de normalização, consulte [criar ou modificar uma regra de normalização no Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md).
  
## <a name="configure-dial-in-conferencing-regions"></a>Configurar as regiões de conferência de discagem
<a name="BKMK_ConfigureDialInRegions"> </a>

Ao configurar um plano de discagem, você especifica a região de conferência discada que se aplica ao plano de discagem. A região de conferência discada associa números de acesso de conferência discada ao plano de discagem apropriado. Ao criar o número de acesso de discagem, selecione as regiões que associam o número de acesso aos planos de discagem apropriados. 
  
Como é importante especificar uma região para todos os planos de discagem, recomendamos usar este procedimento para verificar se todos os planos de discagem têm regiões de conferência. 
  
Para verificar se a região está definida para todos os planos de discagem da conferência discada, use o cmdlet **Get-CsDialPlan**. Se a região não existir nos planos de discagem, você poderá usar o cmdlet **Set-CsDialPlan** para defini-la. Você também pode usar o painel de controle do Skype for Business Server para atualizar a região em planos de discagem existentes. Para obter detalhes sobre como usar o painel de controle do Skype for Business Server, consulte [criar ou modificar um plano de discagem no Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
### <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a>Para verificar se os planos de discagem têm a propriedade de região definida

1. Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**ou **CsAdministrator**.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Execute o seguinte no prompt de comando:
    
   ```
   Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
   ```

   Por exemplo:
    
   ```
   Get-CsDialPlan
   ```

   Neste exemplo, todos os planos de discagem configurados para sua organização são retornados.
    
4. Revise os planos de discagem retornados para identificar todos que estão faltando na região da conferência discada. 
    
Para obter mais informações, consulte [Get-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/get-csdialplan?view=skype-ps).
  
### <a name="to-set-the-region-property-for-a-dial-plan"></a>Para definir a propriedade de região de um plano de discagem

1. Efetue logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**ou **CsAdministrator**.
    
2. Inicie o Shell de Gerenciamento do Skype for Business Server: clique em **Iniciar**, em **Todos os Programas**, em **Skype for Business 2015** e em **Shell de Gerenciamento do Skype for Business Server**.
    
3. Para todos os planos de discagem que não têm a região de conferência discada, execute:
    
   ```
   Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
   ```

   Por exemplo:
    
   ```
   Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
   ```

   Neste exemplo, o plano de discagem com Identidade de Redmond é modificado para definir a propriedade DialinConferencingRegion como "Costa Leste dos EUA". 
    
Para obter mais informações, consulte [set-CsDialPlan](https://docs.microsoft.com/powershell/module/skype/set-csdialplan?view=skype-ps).
  
## <a name="configure-dial-in-access-numbers"></a>Configure números de acesso de discagem
<a name="BKMK_ConfigureDialInAccessNumbers"> </a>

Ao implantar uma conferência discada, você precisa configurar números de telefone que os usuários poderão discar da PSTN para participar da parte de áudio das conferências. Esses números de acesso de discagem aparecem nos convites de reunião e na página Configurações de Conferência Discada.
  
Antes de criar números de acesso discado, primeiro você precisa planejar as regiões de conferência discada e, em seguida, configurar os planos de discagem nas regiões. Para obter detalhes sobre regiões, consulte [planejar a conferência discada no Skype for Business Server](../../plan-your-deployment/conferencing/dial-in-conferencing.md). Para obter detalhes sobre como configurar planos de discagem para conferência discada, consulte [criar ou modificar um plano de discagem no Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md).
  
> [!NOTE]
> Não é possível usar um novo número de acesso discado até que a replicação dos Serviços de Domínio do Active Directory (AD DS) desse número de acesso seja concluída. A replicação pode demorar algumas horas para ser concluída. 
  
> [!NOTE]
> Após a criação dos números de acesso discado, é possível modificar o nome de exibição dos objetos de contato do Active Directory de modo que os usuários possam identificar com mais facilidade o número de acesso correto. Para modificar o nome para exibição, use o cmdlet [set-CsDialInConferencingAccessNumber](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingaccessnumber?view=skype-ps) . Não modifique os objetos do Active Directory manualmente.
  
### <a name="to-create-a-dial-in-access-number"></a>Para criar um número de acesso de discagem

1. Usando uma conta de usuário atribuída à função CsUserAdministrator ou CsAdministrator, faça logon em qualquer computador de sua implantação interna.
    
2. Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação à esquerda, clique em **Conferência** e, então, em  **Número de acesso de discagem**.
    
4. Na página **Número de Acesso de Discagem**, realize uma das ações a seguir:
    
   - Clique em **Novo** para abrir **Novo Número de Acesso de Discagem**.
    
   - Clique em um dos números de acesso de discagem na lista, clique em **Editar**, e clique em **Mostrar detalhes**.
    
     > [!NOTE]
     > Usar o campo de busca para buscar pelos conteúdos de uma coluna na lista de números de acesso de discagem pode não apresentar os resultados esperados. Em vez disso, classifique a lista pela coluna de interesse para identificar o número de acesso de discagem a ser visualizado ou modificado. 
  
5. Em **Número de exibição**, digite o número de telefone que os usuários de telefone da rede telefônica pública comutada (PSTN) digitam para participar de uma conferência. Esse número é exibido em convites de reunião e na página da Web de Configurações de Conferência Discada.
    
6. Em **Nome para exibição**, digite uma descrição para o número de acesso de discagem. Este é o nome associado ao número de acesso de discagem nos resultados da pesquisa do Skype for Business. Esse nome é exibido no cliente quando um usuário disca o número de acesso. 
    
7. Em **URI da Linha**, digite o número E.164 do número de acesso de discagem em formato TEL URI, incluindo o símbolo + antes do número e excluindo espaços. Por exemplo, tel:+14255550200.
    
    > [!NOTE]
    > O mesmo URI de Linha não pode ser reusada por outro número de acesso de conferência discada. 
  
8. Em **URI do SIP**, faça o seguinte:
    
   - Na caixa de texto, digite um único URI do SIP para o número de acesso de conferência discada. Esse URI SIP é exibido em vários locais, incluindo, entre outros, mensagens de notificação de chamada e versões anteriores de clientes do Lync.
    
     > [!NOTE]
     > O mesmo URI do SIP não pode ser reusado por outro número de acesso de conferência discada. O URI do SIP não pode ser modificado depois de o número de acesso ter sido criado. A única maneira de altera o URI do SIP é excluir e recriar o número de acesso. 
  
   - Na caixa de listagem suspensa, clique no domínio do aplicativo de assistente de conferência que dá suporte a esse número de acesso à discagem.
    
9. Em  **Pool**, clique no pool que está executado a instância Atendedor de Conferência que dá suporte ao número de acesso de discagem.
    
    > [!NOTE]
    > Se for preciso alterar o pool depois de criar o número de acesso, deve-se usar o cmdlet do [Move-CsApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/move-csapplicationendpoint?view=skype-ps) ou excluir e recriar o número de acesso.
  
10. Em **Idioma principal**, clique no idioma no qual as solicitações são reproduzidas para esse número de acesso de discagem. 
    
    O idioma principal é o idioma que o Atendente de Conferência usa para atender a ligação. Os idiomas suportados são exibidos ao lado de cada número de acesso de discagem na página da Web das Configurações de Conferência Discada.
    
11. (Opcional) Em **Idiomas secundários (máximo de quatro)**, clique em **Adicionar**, selecione um ou mais idiomas adicionais que você quer oferecer aos chamadores para esse número de acesso de discagem, e clique em **OK**. 
    
    É possível escolher até quatro idiomas secundários para cada número de acesso de discagem. Os usuários podem selecionar um idioma secundário antes de inserir o ID de conferência ao ligarem para uma.
    
12. Para adicionar uma região para o número de acesso de discagem, em **regiões associadas**, clique em **Adicionar**, clique em uma ou mais regiões associadas aos planos de discagem para este número de acesso à discagem e, em seguida, clique em **OK**.
    
13. Para excluir uma região do número de acesso de discagem, em **Regiões Associadas**, clique na região a ser excluída e clique em **Remover**.
    
14. Clique em **Confirmar**.
    
## <a name="configure-conferencing-policies"></a>Configurar políticas de conferência
<a name="BKMK_ConfigureConferencingPolicies"> </a>

A política de conferência é uma configuração de conta de usuário que especifica a experiência de conferência para os participantes. Você pode criar políticas de conferência com um escopo de site ou um escopo de usuário. As configurações de política de conferência englobam vários aspectos do agendamento da conferência e da participação. Várias configurações de política de conferência oferecem suporte à conferência discada para participantes. Ao configurar a conferência discada, você deve verificar se estes campos foram definidos adequadamente para sua organização e modificá-los conforme necessário. 
  
Para obter mais informações sobre como configurar políticas de conferência, consulte [gerenciar políticas de conferência no Skype for Business Server](../../manage/conferencing/conferencing-policies.md).
  
## <a name="assign-a-line-uri-to-a-user-account"></a>Atribuir um URI da Linha a uma conta de usuário
<a name="BKMK_AssignaLineURI"> </a>

Os usuários de discagem digitam o número de telefone ou a extensão e um PIN para participar nas conferências como usuários autenticados. O **URI de linha** de telefonia especificado nas contas de usuário do Skype for Business Server é necessário para autenticação.
  
O procedimento neste tópico descreve como atribuir um **URI da Linha** para uma única conta de usuário. Se você precisar atribuir um **URI da Linha** para várias contas de usuários, poderá criar um script que usa o cmdlet **Set-CsUser**. Para obter detalhes sobre como usar um exemplo de script para atribuir **URI de linha** a várias contas de usuário, consulte [atribuir URIs de linha a vários usuários](https://go.microsoft.com/fwlink/p/?linkId=196945).
  
1. Faça logon no computador como membro do grupo RTCUniversalServerAdmins ou como membro da função **Cs-UserAdministrator** ou **CsAdministrator**.
    
2.  Abra o painel de controle do Skype for Business Server.
    
3. Na barra de navegação esquerda, clique em **Usuários**.
    
4. No campo de pesquisa, digite o nome do usuário que você deseja configurar para conferência discada ou clique em **Adicionar filtro** para especificar os campos de pesquisa e clique em **Localizar**.
    
5. Clique duas vezes no nome do usuário para abrir a caixa de diálogo **Editar Usuário do Skype for Business Server**.
    
6. Em **Telefonia**, no campo **URI da Linha**, digite um número de telefone exclusivo e normalizado (por exemplo, tel:+14255550200).
    
    > [!NOTE]
    > Você pode especificar o **URI de linha** somente se **Telefonia** estiver definida como **Somente PC para PC**, **Enterprise Voice**,  **Controle de chamada remota** ou **Somente controle de chamada remota**. 
  
7. Clique em **Confirmar**.
    

