---
title: 'Lync Server 2013: modificar uma política de voz e configurar registros de uso de PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify a voice policy and configure PSTN usage records
ms:assetid: 6c53aaf5-218b-4bd4-8cea-31bc9d53f1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398511(v=OCS.15)
ms:contentKeyID: 48184419
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ed1aa2d0d08a0f10c9b8b5a6e46e0401cddc61a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>Modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Siga estas etapas para modificar uma política de voz. Se você quiser criar uma nova política de voz, consulte [criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md) para o procedimento.

<div>


> [!NOTE]  
> Se um usuário for atribuído a uma política de voz que não tem registros de uso do PSTN (rede telefônica pública comutada) associados, o usuário não poderá fazer chamadas de saída. Para obter uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice e ver suas propriedades, consulte <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN Usage Records in Lync Server 2013</A>.



</div>

<div>

## <a name="to-modify-a-voice-policy"></a>Para modificar uma política de voz

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz** e em **Política de Voz**.

4.  Na página **Política de Voz**, clique duas vezes em um nome de política de voz.
    
    <div>
    

    > [!NOTE]  
    > O escopo e o nome foram definidos quando a política de voz foi criada. Eles não podem ser alterados.

    
    </div>

5.  (Opcional) Em **Editar Política de Voz**, digite as informações descritivas adicionais para a política de voz.

6.  Marque ou desmarque as seguintes caixas de seleção para habilitar ou desabilitar cada um dos **Recursos de chamada**:
    
      - **Escape de caixa postal** evita que as chamadas sejam encaminhadas imediatamente ao sistema de caixa postal do celular do usuário quando toques simultâneos estão configurados e o telefone está desligado, sem bateria ou sem sinal.
        
        <div>
        

        > [!NOTE]  
        > Este recurso só é configurável por meio do Shell de gerenciamento do Lync Server

        
        </div>
    
      - **Encaminhamento de chamada** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. O Lync Server 2013 oferece uma variedade significativamente maior de opções de configuração para encaminhamento de chamadas. Por exemplo, se uma organização não deseja permitir que as chamadas recebidas sejam encaminhadas externamente à PSTN, um administrador pode aplicar um política de voz especial para implantar essa restrição. Habilitado por padrão.
    
      - **Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. No Lync Server 2013, um representante pode configurar o toque simultâneo, permitindo que as chamadas de entrada para o seu gerente enringem todos os alvos de toque simultâneos do representante. Com isso, o representante tem mais flexibilidade para atender a chamadas direcionadas ao gerente. Habilitado por padrão.
    
      - **Transferência de chamadas** permite os usuários transferirem chamadas para outros usuários. Habilitado por padrão.
    
      - **Estacionamento de chamada** permite os usuários estacionarem chamadas em espera e responderem a chamada de um telefone ou cliente diferente. Desabilitado por padrão.
    
      - **Toque simultâneo** permite as chamadas em entrada tocarem em telefones adicionais (por exemplo, um telefone celular) ou outros dispositivos de ponto de extremidade. O Lync Server 2013 oferece uma variedade significativamente maior de opções de configuração para toque simultâneo. Habilitado por padrão.
    
      - **Chamada de equipe** permite que os usuários de uma equipe definida respondam às chamadas de outros membros da equipe. Habilitado por padrão.
    
      - **Redirecionamento PSTN** permite que as chamadas realizadas pelos usuários atribuídos com esta política para usuários de outras empresas sejam redirecionados em um PSTN (rede telefônica pública comutada) se o WAN estiver congestionado ou indisponível. Habilitado por padrão.
    
      - **Substituir política de largura de banda** permite os administradores substituírem as decisões da política de CAC (controle de admissão de chamada) de um determinado usuário. Desabilitado por padrão.
        
        <div>
        

        > [!NOTE]  
        > A política será substituída apenas para chamadas em entrada do usuário e não para chamadas em saída realizadas pelo usuário. Após a sessão ser estabelecida, o consumo de largura de banda será precisamente registrado. Esta configuração deve ser usada com moderação.

        
        </div>
    
      - **Rastreamento de chamada mal-intencionada** permite os usuários relatarem chamadas mal-intencionadas (como ameaças de bomba) usando o UI cliente, que sinaliza a chamada nos registros de detalhes de chamada (CDRs). Desabilitado por padrão.

7.  Para associar e configurar os registros de uso PSTN para esta política de voz, faça um dos seguintes:
    
      - Para selecionar um ou mais registros em uma lista de todos os registros de uso do PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que deseja associar a esta política de voz e clique em **OK**.
    
      - Para remover um registro de uso PSTN desta política de voz, destaque o registro e clique em **Remover**.
    
      - Para definir um novo registro de uso PSTN e associá-lo com esta política de voz, faça o seguinte:
        
        1.  Clique em **Novo**.
        
        2.  No campo **Nome**, insira um nome descritivo exclusivo para o registro. Por exemplo, você pode desejar criar um registro de uso do PSTN chamado **Redmond** para funcionários efetivos localizados em Redmond e outro registro chamado **RedmondTemps** para funcionários temporários.
            
            <div>
            

            > [!NOTE]  
            > O nome do registro de uso PSTN deve ser exclusivo na implantação do Enterprise Voice. Após o registro ser salvo, o campo <STRONG>Nome</STRONG> não pode ser editado.

            
            </div>
        
        3.  Use qualquer um dos métodos a seguir para associar e configurar roteamentos para este registro de uso PSTN:
            
              - Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.
            
              - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.
            
              - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Clique em **OK**.
    
      - Para editar um registro de uso do PSTN que já está associado a essa política de voz, faça o seguinte:
        
        1.  Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.
        
        2.  Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
            
              - Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.
            
              - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.
            
              - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Clique em **OK**.

8.  Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!NOTE]  
    > A ordem na qual os registros de uso PSTN são listados na política de voz é significante. O Lync Server percorre a lista de cima para baixo. Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

    
    </div>

9.  Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:
    
      - Para usar os mesmos registros de uso do PSTN para encaminhamento de chamadas e toque simultâneo como esta política de voz, selecione a opção **Rotear com usos de PSTN de chamada** no menu suspenso.
    
      - Para permitir o encaminhamento de chamadas e o toque simultâneo somente para usuários internos do Lync, selecione **rotear para usuários internos do Lync somente** no menu suspenso. As chamadas não serão encaminhadas para números PSTN externos.
    
      - Para usar registros de uso do PSTN diferentes dos usados nesta política de voz para encaminhamento de chamadas e toque simultâneo, selecione a opção **Rotear com usos de PSTN personalizados** no menu suspenso. Esta opção exibe um controle para selecionar registros de uso do PSTN existentes ou criar novos registros de uso do PSTN, especificamente para encaminhamento de chamadas e toques simultâneos.
        
          - Para escolher um ou mais registros de uma lista de todos os registros de uso do PSTN para encaminhamento de chamadas e toques simultâneos, clique em **Selecionar**. Realce os registros que deseja associar a esta política de encaminhamento de chamadas e toques simultâneos e clique em **OK**.
        
          - Para remover um registro de uso do PSTN desta política de encaminhamento de chamadas e toques simultâneos, realce o registro e clique em **Remover**.
        
          - Para definir um novo registro de uso do PSTN e associá-lo a essa política de encaminhamento de chamadas e toques simultâneos, faça o seguinte:
            
            1.  Clique em **Novo**.
            
            2.  No campo **Nome**, insira um nome descritivo exclusivo para o registro.
                
                <div>
                

                > [!NOTE]  
                > O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.

                
                </div>
            
            3.  Use qualquer um dos métodos a seguir para associar e configurar roteamentos para este registro de uso PSTN:
                
                  - Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.
                
                  - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.
                
                  - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Clique em **OK**.
        
          - Para editar um registro de uso do PSTN que já está associado a essa política de voz, faça o seguinte:
            
            1.  Realce o registro de uso do PSTN que deseja editar e clique em **Mostrar detalhes**.
            
            2.  Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
                
                  - Para escolher um ou mais rotas na lista de todas as rotas disponíveis na sua implantação do Enterprise Voice, clique em **Selecionar**, destaque as rotas que deseja associar com este registro de uso PSTN e clique em **OK**.
                
                  - Para remover uma rota deste registro de uso PSTN, destaque a rota e clique em **Remover**.
                
                  - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Clique em **OK**.

10. (Opcional) Insira um número para testar a política de voz e clique em **Ir **. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.
    
    <div>
    

    > [!NOTE]  
    > Você pode salvar uma política de voz que ainda não passou no teste e reconfigurá-la mais tarde. Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.

    
    </div>

11. Clique em **OK**.

12. Na página **Política de Voz**, clique em **Confirmar** e em **Confirmar todos**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que criar ou modificar uma política de voz, você deve executar o comando <STRONG>Confirmar todos</STRONG> para publicar a alteração da configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.

    
    </div>

13. (Opcional) O escape de caixa postal detecta que uma chamada foi imediatamente atendida pelo correio de voz do celular do usuário e desconecta a chamada à caixa postal do celular. Isso permite que a chamada continue a tocar nos outros pontos de extremidade do usuário, permitindo que ele atenda à chamada. Para obter detalhes sobre como configurar uma política de caixa postal, consulte [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md)  
[Exibir registros de uso de PSTN no Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Publicar alterações pendentes na configuração de roteamento de voz no Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Configurando o escape de caixa postal no Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  


[Testar roteamento de voz no Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

