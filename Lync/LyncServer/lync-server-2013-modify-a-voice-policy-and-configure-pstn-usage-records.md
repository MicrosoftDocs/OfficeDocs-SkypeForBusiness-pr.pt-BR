---
title: 'Lync Server 2013: modificar uma política de voz e configurar registros de uso de PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb7c4cdc47c0624b3d94d0dc52c527310f803d83
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827183"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>Modificar uma política de voz e configurar registros de uso PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Siga estas etapas se quiser modificar uma política de voz. Se você quiser criar uma nova política de voz, consulte [criar uma política de voz e configurar registros de uso PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) para o procedimento.

<div>


> [!NOTE]  
> Se um usuário estiver atribuído a uma política de voz sem registros de uso PSTN (rede telefônica pública comutada) associados, o usuário não poderá fazer chamadas de saída. Para obter uma lista de todos os registros de uso PSTN disponíveis na sua implantação do Enterprise Voice e exibir suas propriedades, consulte <A href="lync-server-2013-view-pstn-usage-records.md">exibir registros de uso PSTN no Lync Server 2013</A>.



</div>

<div>

## <a name="to-modify-a-voice-policy"></a>Para modificar uma política de voz

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como um membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e, em seguida, insira a URL de administração para abrir o painel de controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [abrir ferramentas administrativas do Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Política de Voz**.

4.  Na página **Política de Voz**, clique duas vezes em um nome de política de voz.
    
    <div>
    

    > [!NOTE]  
    > O escopo e o nome foram definidos quando a política de voz foi criada. Eles não podem ser alterados.

    
    </div>

5.  (Opcional) Em **Editar Política de Voz**, digite as informações descritivas adicionais para a política de voz.

6.  Marque ou desmarque as seguintes caixas de seleção para habilitar ou desabilitar cada um dos **Recursos de chamada**:
    
      - **Escape de caixa postal** impede que chamadas sejam imediatamente encaminhadas ao sistema de caixa postal do telefone celular do usuário quando o toque simultâneo estiver configurado e o telefone estiver desligado, sem bateria, ou fora de área.
        
        <div>
        

        > [!NOTE]  
        > Esse recurso só é configurável por meio do Shell de gerenciamento do Lync Server

        
        </div>
    
      - **Encaminhamento de chamadas** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. O Lync Server 2013 oferece uma gama significativamente mais ampla de opções de configuração para encaminhamento de chamadas. Por exemplo, se uma organização não deseja permitir que chamadas de entrada sejam encaminhadas externamente à PSTN, um administrador por aplicar uma política especial de voz para implantar esta restrição. Habilitado por padrão.
    
      - **Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. No Lync Server 2013, um representante pode configurar o toque simultâneo que permite que as chamadas recebidas para o gerente dele sejam encaminhadas para todos os alvos simultâneos de toque do representante. Isso oferece uma maior flexibilidade ao delegado em responder chamadas direcionadas ao gerente. Habilitado por padrão.
    
      - A **transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.
    
      - **Estacionamento de chamada** permite que os usuários estacionem chamadas em espera e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.
    
      - **Toque simultâneo** permite que as chamadas recebidas toquem em telefones adicionais (por exemplo, um celular) ou outros dispositivos de pontos de extremidade. O Lync Server 2013 oferece uma gama significativamente mais ampla de opções de configuração para toque simultâneo. Habilitado por padrão.
    
      - A **chamada de equipe** permite que os usuários de uma equipe definida atendam às chamadas de outros membros da equipe. Habilitado por padrão.
    
      - O redirecionamento **PSTN** permite chamadas feitas por usuários que recebem essa política para que outros usuários da empresa sejam redirecionados na rede telefônica pública comutada (PSTN) se a WAN estiver congestionada ou indisponível. Habilitado por padrão.
    
      - A **substituição da política de largura de banda** permite que os administradores substituam as decisões da política do controle de admissão de chamadas (CAC) por um usuário específico Desabilitada por padrão.
        
        <div>
        

        > [!NOTE]  
        > A política será substituída apenas para chamadas em entrada do usuário e não para chamadas em saída realizadas pelo usuário. Após a sessão ser estabelecida, o consumo de largura de banda será precisamente registrado. Esta configuração deve ser usada com moderação.

        
        </div>
    
      - O **rastreamento de chamadas maliciosas** permite que os usuários relatem chamadas mal-intencionadas (como as ameaças de bomba) usando a interface do usuário do cliente, que, por sua vez, sinaliza as chamadas nos registros de detalhes da chamada (CDRs). Desabilitado por padrão.

7.  Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:
    
      - Para escolher um ou mais registros de uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de voz e clique em **OK**.
    
      - Para remover um registro de uso de PSTN desta política de voz, realce o registro e clique em **Remover**.
    
      - Para definir um novo registro de uso PSTN e associá-lo a essa política de voz, faça o seguinte:
        
        1.  Clique em **Novo**.
        
        2.  No campo **Nome**, digite um nome descritivo para o registro. Por exemplo, convém criar um registro de uso PSTN chamado **Redmond** para funcionários em tempo integral localizados em Redmond e outro registro chamado **RedmondTemps** para funcionários temporários.
            
            <div>
            

            > [!NOTE]  
            > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.

            
            </div>
        
        3.  Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
            
              - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
            
              - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.
            
              - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Clique em **OK**.
    
      - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:
        
        1.  Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.
        
        2.  Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
            
              - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
            
              - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.
            
              - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Clique em **OK**.

8.  Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!NOTE]  
    > A ordem na qual PSTN registros de uso são listados na diretiva de voz é significativa. O Lync Server percorre a lista de cima para baixo. Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

    
    </div>

9.  Para associar e configurar registros de uso do PSTN para encaminhamento de chamadas e toque simultâneo nesta política de voz, execute um destes procedimentos:
    
      - Para usar os mesmos registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo que esta política de voz, selecione a opção **Encaminhar usando os usos de PSTN da chamada** no menu suspenso.
    
      - Para permitir o encaminhamento de chamadas e o toque simultâneo somente para usuários internos do Lync, selecione encaminhar **para usuários internos do Lync somente** no menu suspenso. Calls will not be forwarded to external PSTN numbers.
    
      - Para usar registros de uso do PSTN diferentes dos usados nesta política de voz para encaminhamento de chamadas e toque simultâneo, selecione a opção **Rotear com usos de PSTN personalizados** no menu suspenso. Esta opção exibe um controle para selecionar registros de uso do PSTN existentes ou criar novos registros de uso do PSTN, especificamente para encaminhamento de chamadas e toques simultâneos.
        
          - Para selecionar um ou mais registros de uma lista de registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de encaminhamento de chamada e toque simultâneo, e então clique em **OK**.
        
          - Para remover um registro de uso de PSTN desta política de encaminhamento de chamadas e toque simultâneo, realce o registro e clique em **Remover**.
        
          - Para definir um novo registro de uso de PSTN e associá-lo a esta política de encaminhamento de chamadas e toque simultâneo, siga estes passos:
            
            1.  Clique em **Novo**.
            
            2.  No campo **Nome**, digite um nome descritivo para o registro.
                
                <div>
                

                > [!NOTE]  
                > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.

                
                </div>
            
            3.  Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
                
                  - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
                
                  - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.
                
                  - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Clique em **OK**.
        
          - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:
            
            1.  Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.
            
            2.  Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
                
                  - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK**.
                
                  - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.
                
                  - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Clique em **OK**.

10. (Opcional) Insira um número para testar a política de voz e clique em **Ir**. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.
    
    <div>
    

    > [!NOTE]  
    > Você pode salvar uma política de voz que ainda não passou no teste e, em seguida, reconfigurá-lo posteriormente. Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.

    
    </div>

11. Clique em **OK**.

12. Na página **Política de Voz**, clique em **Confirmar** e clique em **Confirmar tudo**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que criar ou modificar uma política de voz, você deve executar o comando <STRONG>Confirmar todos</STRONG> para publicar a alteração da configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013</A> na documentação de operações.

    
    </div>

13. (Opcional) O escape de caixa postal detecta que uma chamada foi imediatamente atendida pelo correio de voz do celular do usuário e desconecta a chamada à caixa postal do celular. Isso permite que a chamada continue a tocar nos outros pontos de extremidade do usuário, permitindo que ele atenda à chamada. Para obter detalhes sobre como configurar uma política de caixa postal, consulte Configurando o [recurso de mensagem de voz no Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Exibir registros de uso de PSTN no Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Configurando o recurso de mensagem de voz no Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  


[Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

