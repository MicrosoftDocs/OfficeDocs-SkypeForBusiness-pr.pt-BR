---
title: Gerenciar 9-1-1 aprimorado e o serviço de Localização
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: O Skype for Business Server dá suporte à chamada 9-1-1 (E9-1-1) aprimorada de clientes do Skype for Business. Quando você configura o Skype for Business Server para E9-1-1, as chamadas de emergência feitas do Skype for Business incluem informações de ERL (Local de Resposta a Emergência) do banco de dados do serviço de Informações de Local.
ms.openlocfilehash: c5b626763de78495a2feaa5ecb1ba77e367bd77d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817471"
---
# <a name="manage-enhanced-9-1-1-and-the-location-service-in-skype-for-busines-server"></a>Gerenciar 9-1-1 aprimorado e o serviço de Localização no Skype for Busines Server

O Skype for Business Server dá suporte à chamada 9-1-1 (E9-1-1) aprimorada de clientes do Skype for Business. Quando você configura o Skype for Business Server para E9-1-1, as chamadas de emergência feitas do Skype for Business incluem informações de ERL (Local de Resposta a Emergência) do banco de dados do serviço de Informações de Local. Use os procedimentos deste artigo para gerenciar a política de local.

> [!Note]
> Para obter detalhes sobre como implantar recursos avançados do Enterprise Voice, como o E9-1-1 e o serviço informações de local, consulte Implantar recursos avançados [do Enterprise Voice.](../deploy/deploy-enterprise-voice/deploy-advanced-enterprise-voice-features.md)

No Skype for Business Server, você pode usar a política de local para aplicar configurações relacionadas à funcionalidade do Enhanced 9-1-1 (E9-1-1) e às configurações de local para usuários ou contatos. A política de local determina se o usuário está habilitado para o E9-1-1 e, se estiver, qual vai ser o comportamento de uma chamada de emergência. Por exemplo, é possível usar a política de local para definir o número que constitui uma chamada de emergência (911 nos Estados Unidos), se a segurança da empresa deve ser automaticamente notificada e como a chamada é roteada.

Você pode configurar políticas de local do grupo **Configuração de** Rede no Painel de Controle do Skype for Business Server. No Painel de Controle do Skype for Business Server, você pode exibir, criar, modificar ou excluir políticas de local. Use o procedimento a seguir para exibir informações sobre políticas de local. 


## <a name="view-location-policy-information"></a>Exibir informações de política de local 

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Política de Local.**

4.  Na página **Política de local**, selecione a política de local que você quer modificar.

5.  No menu **Editar**, clique em **Mostrar detalhes**.
 
    > [!NOTE]  
    > Você pode visulizar informações apenas de uma política de local por vez.

Uma política única, chamada de Global, existe por padrão e não pode ser excluída ou renomeada. Porém, você pode modificar a política Global. Essa política será aplicada a todos os usuários e contatos, a não ser que você crie políticas de sites ou políticas por usuário. As políticas por usuário devem ser aplicadas a usuários específicos.


## <a name="create-or-modify-a-location-policy"></a>Criar ou modificar uma política de local 

No Skype for Business Server, você pode substituir o período padrão entre solicitações de cliente para uma atualização de local do serviço de Informações de Local. O valor padrão é de 4 horas. Use o cmdlet **Set-CsLocationPolicy** com o parâmetro LocationRefreshInterval para substituir o valor padrão.


### <a name="to-create-a-new-location-policy-in-the-skype-for-business-server-control-panel"></a>Para criar uma nova política de local no Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Política de Local.**

4.  Na página **Política de** Local, clique em **Novo** e selecione o tipo de política que você deseja criar:
    
      - Para criar uma política de site, clique em **Política de site.** Em **Selecionar um Site,** escolha o site ao qual você deseja aplicar a política e clique em **OK.** Na página Nova **Política de** Local, **o** campo  Escopo contém o valor **Site** e o campo Nome contém o nome do site escolhido. Não é possível modificar nenhum desses campos. Uma política de site é aplicada automaticamente a todos os usuários no site especificado e substitui a política global para esses usuários.
    
      - Para criar uma **política de usuário,** clique **em Política de usuário.** In the **New Location Policy**, the **Scope** field contains the value **User**. Não é possível modificar esse valor. No campo **Nome,** digite o nome que você deseja dar a essa política. Uma política de usuário não se aplica automaticamente a nenhum usuário. Depois de criar a política de usuário, você deve conceder manualmente a política aos usuários ou sites de rede aos quais deseja aplicar a política.

5.  Preencha os campos restantes da seguinte forma:
    
      - **Habilitar serviços de emergência aprimorados**   Marque essa caixa de seleção para habilitar os usuários associados a essa política para E9-1-1. Quando os serviços de emergência estão habilitados, os clientes do Skype for Business Server recuperarão as informações de local no registro e incluirão essas informações quando uma chamada de emergência for feita.
    
      - **Localização**   Especifique um dos seguintes valores:
        
          - **Obrigatório**   O usuário será solicitado a inserir informações de local quando se registrar em um novo local. O usuário pode recusar o aviso, sem digitar qualquer informação. Se as informações são inseridas, uma chamada de emergência será atendida primeiro pelo provedor de serviços de emergência para verificar o local antes de ser roteada para o operador PSAP (Ponto de Atendimento Público Seguro) (ou seja, o operador 911).
        
          - **Não obrigatório**   O usuário não será solicitado a localizar. Quando uma chamada é feita sem informações de local, o provedor de serviços de emergência atenderá à chamada e solicitará um local.
        
          - **Aviso de isenção de responsabilidade**   Essa opção é a mesma que **Required,** exceto pelo fato de que o usuário não pode descartar a solicitação sem inserir informações de local. O usuário ainda pode concluir uma chamada de emergência, mas nenhuma outra chamada pode ser concluída sem inserir as informações. Além disso, o texto do aviso de isenção de responsabilidade será exibido para o usuário que pode alertá-lo para as consequências de se negar a inserir informações de localização. Para definir o texto do aviso de isenção de responsabilidade, você deve usar o Shell de Gerenciamento do Skype for Business Server para executar o cmdlet **Set-CsLocationPolicy** ou o cmdlet **New-CsLocationPolicy** com o parâmetro EnhancedEmergencyServiceDisclaimer. Para obter detalhes, [consulte Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) ou [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy).
          
    
      - **Use location for emergency services only** O Skype for Business pode usar informações de localização por vários motivos (por exemplo, para notificar colegas de equipe sobre sua localização atual). Marque essa caixa de seleção para garantir que as informações de local só estarão disponíveis para uso com uma chamada de emergência.
    
      - **Uso de PSTN**   O uso da PSTN (Rede Telefônica Pública Comutado) que será usada para determinar qual rota de voz será usada para encaminhar chamadas de emergência de clientes que usam esse perfil. A rota associada a esse uso deve apontar para um tronco SIP dedicado a chamadas de emergência ou a um gateway de Emergency Location Identification Number (ELIN) que encaminha as chamadas de emergência ao Public Safety Answering Point (PSAP) mais próximo.
    
      - **Número de discagem de emergência**   O número discado para alcançar os serviços de emergência. Nos Estados Unidos, esse valor é 911. A cadeia de caracteres deve ser composta pelos dígitos 0 a 9 e pode ter entre um e dez dígitos de comprimento.
    
      - **Máscara de discagem de emergência**   Um número que você deseja converter no valor do número de discagem de emergência quando discado. Por exemplo, se você inserir um valor 212 nesse campo e o campo de número de discagem de emergência tiver o valor 911, se um usuário discar 212, a chamada será feita para 911. Isso permite a discagem de números de emergência alternativos e ainda assim acessar os serviços de emergência (por exemplo, se alguém de um país ou região com um número de emergência diferente tenta discar o número desse país ou região em vez do número para o país ou região atual). É possível definir múltiplas máscaras de discagem de emergência separando os valores com ponto e vírgulas. Por exemplo, 212;414. O comprimento máximo da cadeia de caracteres é 100. Cada caractere deve ser um dígito entre 0 e 9.
      

        > [!IMPORTANT]  
        > Garanta que o valor da máscara de discagem especificado não seja igual a um número no intervalo da órbita de estacionamento de chamadas. O roteamento do estacionamento de chamadas terá precedência sobre a conversão de cadeias de caracteres de discagem de emergência. Para ver os intervalos de órbitas existentes do estacionamento de chamadas, clique em **Recursos** de Voz na barra de navegação esquerda e clique em **Estacionamento de Chamadas.** 

    
      - **URI de notificação**   Um ou mais URIs (Uniform Resource Identifiers) SIP para serem notificados quando uma chamada de emergência for feita. Por exemplo, o escritório de segurança da empresa poderia ser avisado, por meio de uma mensagem instantânea, sempre que ocorrer uma chamada de emergência. Se a localização do chamador estiver disponível, ela será incluída na notificação. Vários URIs do SIP podem ser incluídos como uma lista separada por vírgulas. Por exemplo, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com". As listas de distribuição são suportadas. A string precisa ter de 1 a 256 caracteres e precisa começar com o prefixo "sip:". Antes de clicar no campo URI de Notificação, um exemplo é exibido.
    
      - **URI de conferência**   O URI do SIP, neste caso, o número de telefone de um terceiro que será conferênciado para qualquer chamada de emergência realizada. Por exemplo, o escritório de segurança da empresa poderia receber uma chamada quando uma chamada de emergência  é feita e ouvir ou participar dessa chamada (dependendo do valor fornecido no campo modo conferência). A cadeia de caracteres deve ter entre um e 256 caracteres de comprimento e deve começar com o prefixo sip:. Um exemplo é exibido até você clicar dentro desse campo.
    
      - **Modo de conferência**   Se você especificar um valor no campo  **URI** de Conferência, o modo conferência determinará se um terceiro pode participar da chamada ou somente escutar. Especifique uma das seguintes opções:
        
          - **One-way**   Um terceiro só pode ouvir a conversa entre o chamador e o operador PSAP.
        
          - **Duas vias**   Um terceiro pode escutar e participar da chamada entre o chamador e o operador PSAP.

6.  Clique em **Confirmar**.


    > [!IMPORTANT]  
    > Quando você cria uma política de usuário, inicialmente essa política não se aplica a usuários ou sites de rede. Para aplicar a política a um usuário, clique **em Usuários** na barra de navegação esquerda. Encontre o usuário ao qual você deseja aplicar a política. No painel **Ações**, clique em **Mostrar detalhes**. Na página **Editar Usuário do Servidor,** selecione  a nova política de local na lista drop-down da política de local e clique em **Confirmação.**<BR>Para aplicar a política a um site de rede, clique em **Configuração** de Rede na barra de navegação esquerda e clique em **Site.** Encontre o site de rede ao qual você deseja aplicar a política. No painel **Ações**, clique em **Mostrar detalhes**. Em **Editar Site,** selecione a nova política de local na **lista** de lista drop-down da política de local e clique em **Confirmação.**


### <a name="to-modify-a-location-policy-in-the-skype-for-business-server-control-panel"></a>Para modificar uma política de local no Painel de Controle do Skype for Business Server

1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Política de Local.**

4.  Na página **Política de local**, selecione a política de local que você quer modificar.

5.  No menu **Editar**, clique em **Mostrar detalhes**.

6.  Na página **Editar** Política de Local, modifique os campos conforme necessário (para obter detalhes, consulte a Etapa 5 nos procedimentos "Para criar uma nova política de local" anteriormente neste tópico).

7.  Clique em **Confirmar**.

        
## <a name="delete-a-location-policy"></a>Excluir uma política de local


1.  Em uma conta de usuário que seja membro do grupo RTCUniversalServerAdmins (ou que tenha direitos de usuário equivalentes) ou que tenha a função CsAdministrator atribuída, faça logon em qualquer computador em sua implantação interna.

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Skype for Business Server. 

3.  Na barra de navegação esquerda, clique em **Configuração de** Rede e em **Política de Local.**

4.  Na página **Política de local**, selecione a política de local que você quer excluir.
   
    > [!NOTE]  
    > Você pode excluir mais que uma política de local ao mesmo tempo. Para isso, mantenha a tecla CTRL e selecione várias políticas. Ou, para selecionar todas as políticas, clique em **Selecionar tudo** no menu **Editar**.


5.  No menu **Editar**, clique em **Excluir**.

6.  Clique em **OK**.

    > [!IMPORTANT]  
    > Você não pode excluir uma política de local Global. Se você tentar excluir a política Global, você receberá uma mensagem de aviso, e essa política será redefinida aos seus valores padrão.


## <a name="see-also"></a>Confira também

[Criar ou modificar sites de rede](network-management/call-admission-control/managing-call-admission-control-for-sites.md#create-or-modify-network-sites)

[New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsLocationPolicy)  

[Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsLocationPolicy) 
 
[Remove-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsLocationPolicy)  

[Get-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsLocationPolicy)  
