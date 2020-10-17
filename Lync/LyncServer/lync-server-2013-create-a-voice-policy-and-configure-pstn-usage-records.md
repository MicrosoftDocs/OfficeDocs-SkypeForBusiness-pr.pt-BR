---
title: 'Lync Server 2013: criar uma política de voz e configurar registros de uso de PSTN'
description: 'Lync Server 2013: Crie uma política de voz e configure registros de uso de PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 55833572b5ca79019d5037406ae530ef5591b6fe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562447"
---
# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>Criar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-01_

Siga essas etapas se quiser criar uma nova política de voz. Se você quiser editar uma política de voz, consulte [modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) para o procedimento.

<div>


> [!NOTE]  
> Cada política de voz precisa ter pelo menos um registro de uso de PSTN (Rede Telefônica Pública Comutada) associada. Para ver uma lista de todos os registros de uso de PSTN disponíveis em sua implantação do Enterprise Voice e ver suas propriedades, consulte <A href="lync-server-2013-view-pstn-usage-records.md">View PSTN Usage Records in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-voice-policy"></a>Para criar uma política de voz

1.  Faça logon no computador como um membro do grupo RTCUniversalServerAdmins ou como membro da função CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Para obter detalhes, consulte [delegar permissões de configuração no Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Abra uma janela do navegador e insira a URL do Administrador para abrir o Painel de Controle do Lync Server. Para obter detalhes sobre os diferentes métodos que você pode usar para iniciar o painel de controle do Lync Server, consulte [Open Lync server 2013 Administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Na barra de navegação esquerda, clique em **Roteamento de Voz** e clique em **Política de Voz**.

4.  Na página **Política de Voz**, clique em **Novo** e selecione um escopo para a nova política:
    
      - **Política do site** se aplica a todo um site, exceto algum usuário ou grupo que tenha recebido uma política de usuário. Se você selecionar Site para um escopo de política, escolha o site na caixa de diálogo **Selecionar um Site**. Se uma política de voz tiver sido criada para um site, o site não aparece na caixa de diálogo **Selecionar um Site**.
    
      - **Política de usuário** pode ser aplicado a usuários ou grupos especificados.

5.  Se o escopo da política de voz for Usuário, digite um nome descritivo para a política no campo **Nome**.
    
    <div>
    

    > [!NOTE]  
    > Se o escopo da política de voz for Site, o campo <STRONG>Nome</STRONG> na <STRONG>Nova Política de Voz</STRONG> será pré-preenchido com o nome do site e não poderá ser alterado.

    
    </div>

6.  (Opcional) Insira informações descritivas adicionais para a política de voz.

7.  Marque ou desmarque as caixas de seleção a seguir para habilitar ou desabilitar cada um dos **Recursos de chamada** para esta política de voz:
    
      - **Escape de caixa postal** impede que chamadas sejam imediatamente encaminhadas ao sistema de caixa postal do telefone celular do usuário quando o toque simultâneo estiver configurado e o telefone estiver desligado, sem bateria, ou fora de área.
        
        <div>
        

        > [!NOTE]  
        > Este recurso só é configurável por meio do Shell de gerenciamento do Lync Server

        
        </div>
    
      - **Encaminhamento de chamada** permite que os usuários encaminhem chamadas a outros telefones e dispositivos clientes. O Lync Server 2013 oferece uma variedade significativamente maior de opções de configuração para encaminhamento de chamadas. Por exemplo, se uma organização não deseja permitir que as chamadas recebidas sejam encaminhadas externamente à PSTN, um administrador pode aplicar um política de voz especial para implantar essa restrição. Habilitado por padrão.
    
      - **Delegação** permite que o usuário especifique outros usuários para enviar e receber chamadas em seu nome. No Lync Server 2013, um representante pode configurar o toque simultâneo, permitindo que as chamadas de entrada para o seu gerente enringem todos os alvos de toque simultâneos do representante. Com isso, o representante tem mais flexibilidade para atender a chamadas direcionadas ao gerente. Habilitado por padrão.
    
      - **Transferência de chamada** permite a transferência de chamadas para outros usuários. Habilitado por padrão.
    
      - **Estacionamento de chamada** permite que os usuários estacionem chamadas em espera e atendam à chamada de um telefone ou cliente diferente. Desabilitado por padrão.
    
      - **Toque simultâneo** permite as chamadas em entrada tocarem em telefones adicionais (por exemplo, um telefone celular) ou outros dispositivos de ponto de extremidade. O Lync Server 2013 oferece uma variedade significativamente maior de opções de configuração para toque simultâneo. Habilitado por padrão.
    
      - **Chamada de equipe** permite que os usuários de uma equipe definida respondam às chamadas de outros membros da equipe. Habilitado por padrão.
    
      - **Redirecionamento de PSTN** permite que as chamadas realizadas por usuários que receberam essa política para outros usuários empresariais sejam redirecionadas na PSTN (Rede Telefônica Pública Comutada) se a WAN estiver congestionada ou indisponível. Habilitado por padrão.
    
      - **Substituição da política de largura de banda** permite que os administradores substituam as decisões da política de controle de admissão de chamada para um usuário específico. Desabilitada por padrão.
        
        <div>
        

        > [!NOTE]  
        > A política será substituída somente para chamadas de entrada para o usuário e não para chamadas de saída feitas pelo usuário. Após o estabelecimento da sessão, o consumo de largura de banda será registrado de forma precisa. Essa configuração deve ser usada com moderação e deve ser reservado em prol de decisões apropriadas de controle de chamada.

        
        </div>
    
      - **Rastreamento de chamada mal-intencionada** permite que os usuários reportem chamadas mal intencionadas (como ameaças de bomba) usando a UI do cliente, o que por sua vez marca as chamadas nos CDRs (registros de detalhe da chamada). Desabilitado por padrão.

8.  Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:
    
      - Para selecionar um ou mais registros em uma lista de todos os registros de uso do PSTN disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**. Realce os registros que deseja associar a esta política de voz e clique em **OK**.
    
      - Para remover um registro de uso PSTN desta política de voz, destaque o registro e clique em **Remover**.
    
      - Para definir um novo registro de uso PSTN e associá-lo com esta política de voz, faça o seguinte:
        
        1.  Clique em **Novo**.
        
        2.  No campo **Nome**, digite um nome descritivo para o registro. Por exemplo, convém criar um registro de uso PSTN chamado **Redmond** para funcionários em tempo integral localizados em Redmond e outro chamado **RedmondTemps** para funcionários temporários.
            
            <div>
            

            > [!NOTE]  
            > O nome do registro de uso de PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.

            
            </div>
        
        3.  Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
            
              - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar **, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK **.
            
              - Para remover uma rota do registro de uso do PSTN, realce a rota e então clique em **Remover**.
            
              - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Clique em **OK**.
    
      - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:
        
        1.  Realce o registro de uso do PSTN que você deseja editar e então clique em **Mostrar detalhes**.
        
        2.  Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
            
              - Para escolher uma ou mais rotas da lista de todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar **, realce as rotas que você deseja associar a esse registro de uso do PSTN e clique em **OK **.
            
              - Para remover uma rota desse registro de uso do PSTN, realce a rota e então clique em **Remover**.
            
              - Para definir uma nova rota e associar esse registro de uso do PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Para editar uma rota que já está associada a esse registro de uso do PSTN, realce a rota e clique em **Mostrar detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Clique em **OK**.

9.  Organize os registros de uso do PSTN para obter o melhor desempenho. Para alterar a posição de um registro na lista, realce o nome de registro e clique na seta para cima ou para baixo.
    
    <div>
    

    > [!IMPORTANT]  
    > A ordem na qual os registros de uso PSTN são listados na política de voz é significante. O Lync Server percorre a lista de cima para baixo. Recomendamos que você organize a lista por frequência de uso, por exemplo: RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

    
    </div>

10. Para associar e configurar registros de uso do PSTN para essa política de voz, execute um destes procedimentos:
    
      - Para usar os mesmos registros de uso de PSTN para enchaminhamento de chamadas e toque simultâneo que esta política de voz, selecione a opção **Encaminhar usando os usos de PSTN da chamada** no menu suspenso.
    
      - Para permitir enchaminhamento de chamadas e toque simultâneo apenas a usuários internos do Lync, selecione a opção **Encaminhar apenas para usuários internos do Lync** no menu suspenso. As chamadas não serão encaminhadas para números PSTN externos.
    
      - Para especificar registros de uso de PSTN diferentes para encaminhamento de chamadas e toque simultâneos que os usados para esta política de voz, selecione a opção **Encaminhar usando usos de PSTN personalizados** no menu suspenso. Essa opção exibe um controle para selecionar registros de uso de PSTN existentes ou criar novos registros de uso de PSTN especificamente para encaminhamento de chamadas e toque simultâneo.
        
          - Para selecionar um ou mais registros de uma lista de registros de uso de PSTN para encaminhamento de chamadas e toque simultâneo, clique em **Selecionar**. Realce os registros que você deseja associar a essa política de encaminhamento de chamada e toque simultâneo, e então clique em **OK**.
        
          - Para remover um registro de uso do PSTN desta política de encaminhamento de chamadas e toques simultâneos, realce o registro e clique em **Remover**.
        
          - Para definir um novo registro de uso do PSTN e associá-lo a essa política de encaminhamento de chamadas e toques simultâneos, faça o seguinte:
            
            1.  Clique em **Novo**.
            
            2.  No campo **Nome**, insira um nome descritivo exclusivo para o registro.
                
                <div>
                

                > [!NOTE]  
                > O nome do registro de uso do PSTN deve ser exclusivo dentro de implantação do Enterprise Voice. Após a gravação do registro, o campo <STRONG>Nome</STRONG> não pode ser editado.

                
                </div>
            
            3.  Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
                
                  - Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.
                
                  - Para remover uma rota do registro de uso do PSTN, realce a rota e clique em **Remover**.
                
                  - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Clique em **OK**.
        
          - Para editar um registro de uso de PSTN que já está associado a essa política de voz, faça o seguinte:
            
            1.  Realce o registro de uso do PSTN que você deseja editar e clique em **Mostrar detalhes**.
            
            2.  Use qualquer um dos métodos a seguir para associar e configurar rotas para este registro de uso do PSTN:
                
                  - Para selecionar uma ou mais rotas da lista com todas as rotas disponíveis em sua implantação do Enterprise Voice, clique em **Selecionar**, realce as rotas que deseja associar a este registro de uso do PSTN e clique em **OK**.
                
                  - Para remover uma rota desse registro de uso do PSTN, realce a rota e clique em **Remover**.
                
                  - Para definir uma nova rota e associá-la com este registro de uso PSTN, clique em **Novo**. Para obter detalhes, consulte [criar uma rota de voz no Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Para editar uma rota já associada com este registro de uso PSTN, destaque a rota e clique em **Exibir detalhes**. Para obter detalhes, consulte [modificar uma rota de voz no Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Clique em **OK**.

11. (Opcional) Insira um número para testar a política de voz e clique em **Ir **. Os resultados do teste são exibidos em **Número convertido para fazer um teste**.
    
    <div>
    

    > [!NOTE]  
    > Você pode salvar uma política de voz que ainda não passou no teste e reconfigurá-la mais tarde. Para obter detalhes, consulte <A href="lync-server-2013-test-voice-routing.md">testar o roteamento de voz no Lync Server 2013</A>.

    
    </div>

12. Clique em **OK**.

13. Na página **Política de Voz**, clique em **Confirmar** e em **Confirmar todos**.
    
    <div>
    

    > [!NOTE]  
    > Sempre que você criar ou modificar uma política de voz, será necessário executar o comando <STRONG>Confirmar tudo</STRONG> para publicar a alteração de configuração. Para obter detalhes, consulte <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publish Pending Changes to The Voice Routing Configuration in Lync Server 2013</A> na documentação operações.

    
    </div>

14. (Opcional) O escape de caixa postal detecta que uma chamada foi imediatamente atendida pelo correio de voz do celular do usuário e desconecta a chamada à caixa postal do celular. Isso permite que a chamada continue a tocar nos outros pontos de extremidade do usuário, permitindo que ele atenda à chamada. Para obter detalhes sobre como configurar uma política de caixa postal, consulte [Configuring voice mail escape in Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

</div>

<div>

## <a name="see-also"></a>Confira também


[Modificar uma política de voz e configurar registros de uso de PSTN no Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
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

