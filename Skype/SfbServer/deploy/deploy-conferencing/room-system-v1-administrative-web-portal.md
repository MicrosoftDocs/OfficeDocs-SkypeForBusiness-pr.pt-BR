---
title: Implantar o portal da Web administrativo do SRS v1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: Os sistemas de salas Skype v1 do Skype for Business Server v1 (SRS v1, anteriormente conhecido como sistema de sala do Lync) é um portal da Web que as organizações podem usar para manter seus sistemas de salas de conferência do Skype. Os administradores podem usar o portal da Web administrativo do SRS v1 para monitorar a integridade do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.
ms.openlocfilehash: 5ad4ffb08ecbc32feaa87aa2f7d48d82003e2e3e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34307158"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Implantar o portal da Web administrativo do SRS v1 no Skype for Business Server

Os sistemas de salas Skype v1 do Skype for Business Server v1 (SRS v1, anteriormente conhecido como sistema de sala do Lync) é um portal da Web que as organizações podem usar para manter seus sistemas de salas de conferência do Skype. Os administradores podem usar o portal da Web administrativo do SRS v1 para monitorar a integridade do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.

Para usar esse recurso, o portal da Web administrativo do SRS v1 precisa ser implantado em cada servidor front-end do Skype for Business Server. Este guia fornece instruções para os administradores sobre como instalar e configurar o Portal da Web Administrativo do SRS. Destina-se a administradores que têm conhecimento da administração do Skype for Business Server e têm direitos de usuário de administrador para modificar a topologia do Skype for Business Server.

Depois que o portal da Web administrativo do SRS v1 é implantado no servidor, os administradores podem verificar o status dos dispositivos SRS v1 ao fazer logon no site de seus próprios computadores ou laptops.

> [!IMPORTANT]
> Baixe o [portal da Web administrativo Microsoft Skype Room Systems v1 para o Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).

Neste tópico:

- [Configurar seu ambiente para o Portal da Web Administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Instalar o portal da Web administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Usar o Portal da Web Administrativo do SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configurar seu ambiente para o Portal da Web Administrativo do SRS v1
<a name="Config_Env"> </a>

Para usar o Portal da Web Administrativo do SRS v1, será necessário instalar ou configurar os pré-requisitos a seguir.

> [!IMPORTANT]
> Se o servidor estiver configurado com a autenticação Kerberos e NTLM e o SRS estiver em execução em um computador que não tenha ingressado no domínio, haverá falha na autenticação Kerberos e o usuário não verá o status do SRS no portal administrativo. Para resolver esse problema, configure o servidor com autenticação NTLM ou com autenticação NTLM e TLS-DSK (sem Kerberos), ou ingresse o computador com SRS no domínio.

1. Instale as atualizações cumulativas do Skype for Business Server na topologia do Skype for Business Server.

    Para obter a atualização ou ver o que está incluído nele, confira [atualizações para o Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).

2. Crie um usuário do Active Directory habilitado para SIP.

    O portal da Web administrativo do SRS v1 usa essas credenciais para consultar informações do Skype for Business Server. O nome de usuário nos exemplos fornecidos é LRSApp.

3. Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.

    Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que forem adicionados a este grupo serão autorizados a ver a lista de salas e a executar determinados comandos, como coletar logs.

4. Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup.

    Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que forem adicionados a esse grupo serão autorizados a usar toda a funcionalidade do portal de administração em uma única sala do Skype. Para incluir suporte para o gerenciamento em massa de salas do Skype, consulte a etapa 5. 

     ![Lista de grupos de administradores com função de grupo de segurança](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Crie um grupo de segurança do Active Directory com o nome LRSPowerUserAdminsGroup.

    Crie o grupo com Escopo do Grupo como Global e Tipo de Grupo como Segurança. Os usuários habilitados para SIP que são adicionados a este grupo têm autorização para usar toda a funcionalidade do portal de administração, incluindo o gerenciamento em massa de salas do Skype for Business.

6. Adicione LRSFullAccessAdminGroup como um membro de LRSSupportAdminGroup.

     ![Página de membros de propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Crie um usuário do Active Directory compatível com SIP com o nome LRSSupport. Adicione este usuário ao LRSSupportAdminGroup.

     ![Página de membros de propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Instale o [ASP.NET MVC 4 para Visual Studio 2010 SP1 e Visual Web developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Instalar o portal da Web administrativo do SRS v1
<a name="Install_SRS"> </a>

Baixe o [portal da Web administrativo Microsoft Skype Room Systems v1 para o Skype for Business Server 2015](https://www.microsoft.com/en-us/download/details.aspx?id=46906).

Para instalar o portal da Web administrativo do SRS v1, use as etapas a seguir.

1. Configure a porta de aplicativo confiável executando o seguinte cmdlet no Shell de gerenciamento do Skype for Business Server:

   ```
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Para instalar o portal da sala de reunião, baixe o **MeetingRoomPortalInstaller. msi** e, em seguida, execute-o como administrador.

3. Abra o arquivo Web. config do seguinte local:

    % Program Files%\Skype for Business Server 2015 \ Web Components\Meeting sala Portal\Int\Handler\

4. No arquivo Web. config, altere o PortalUserName para o nome de usuário criado na etapa 2 na seção "[configurar seu ambiente para o portal da Web administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (o nome recomendado na etapa é LRSApp):

    ```
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Como o portal de administração do SRS v1 é um aplicativo confiável, você não precisa fornecer a senha na configuração do Portal. Se esse usuário estiver usando um registrador diferente do registrador local, você precisará especificar o registrador para ele adicionando a seguinte linha no arquivo Web. config:

   ```
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Se a porta usada for diferente de 5061, adicione a seguinte linha no arquivo Web. config:

   ```
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Verificar a instalação do portal da Web administrativo do SRS

Para verificar a instalação do portal da Web administrativo do SRS v1, faça o seguinte:

1. Em um servidor front-end, navegue até a seguinte URL:

    https://\<FE-servidor\>/lRS

    Você não verá nenhum erro, conforme mostrado na imagem a seguir:

     ![Tela de entrada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortalSignIn.png)

2. Se você não vir nenhum erro, tente acessar a seguinte URL a partir de qualquer outro computador na topologia:

    https://\<FE-servidor\>/lRS

    Para acessar a página, você precisará adicionar os registros DNS conforme descrito em "[registros de DNS necessários para a entrada automática do cliente](https://go.microsoft.com/fwlink/p/?LinkId=318056)".

## <a name="use-the-srs-administrative-web-portal"></a>Usar o Portal da Web Administrativo do SRS
<a name="Use_Portal"> </a>

Depois de implantar o SRS no servidor, você pode verificar o status de todas as salas SRS ao entrar no portal da Web administrativo do SRS V1 a partir de um navegador.

### <a name="sign-in"></a>Entrar

1. Acesse a seguinte URL:

    https://\<FE-servidor\>/lRS

2. Insira as credenciais para a conta LRSSupport ou uma conta que foi adicionada ao grupo de segurança LRSSupportAdminGroup.

![Tela de entrada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Página de resumo do portal de Web administrativo do SRS

A página Resumo fornece as seguintes informações para todas as salas SRS implantadas no servidor:

- **Marca de formatação** O nome personalizado que o administrador fornece à sala. A marca pode ser definida no portal clicando no nome da sala.

- **Integridade** do O status de integridade da sala, que é derivado do status de integridade da agregação da sala, que é mostrado na seção integridade da página de configurações da sala.

- **Próxima reunião** A data e a hora em que a próxima reunião está agendada.

- **Versão do SRS, fabricante, modelo** Esses valores são predefinidos no SRS. Dependendo do fabricante, esses campos podem ser deixados em branco.

- **Última atualização** Exibe a última vez que a página da Web foi atualizada.

![Exibição resumida do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Você só verá o menu gerenciamento em massa se fizer parte do grupo de segurança LRSPowerUserAdminsGroup.

### <a name="srs-room-information"></a>Informações da sala de SRS

A seção informações da sala do portal permite que você visualize e configure salas individuais de SRS. Ele contém quatro seções: configurações, detalhes, registro em log e integridade.

#### <a name="settings"></a>Configurações

Na seção Configurações, você pode definir a senha, a marca de sala e os níveis de volume padrão da sala. Se você definir essas configurações, as alterações serão replicadas somente após a reinicialização do console do SRS. Você só verá as configurações de atualizações do sistema para dispositivos SRS usando o Release 15,12 e posteriores.

![Configurações da sala do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Detalhes

A seção detalhes fornece um resumo somente leitura das configurações da sala de SRS, incluindo: o tempo da última atualização; próxima reunião; últimas atualizações, manutenção e calibragem; configurações de alto-falante, microfone e toque padrão; versões URI SIP; número de telas e detalhes sobre cada tela; status e atividade.

![Visão detalhada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Solução de problemas

A seção solução de problemas pode ser usada para coletar logs remotamente e salvá-los em um local específico. Você também pode reiniciar o console do SRS (interface do usuário do SRS) ou reiniciar o sistema inteiro. Para coletar logs, forneça um caminho de pasta no formato especificado e certifique-se de que a pasta tenha permissões de gravação atribuídas à conta de máquina do SRS. Se o tamanho do log for muito grande, pode levar até 5 minutos para concluir a coleta de logs. A atualização da página dará o status mais recente.

#### <a name="health"></a>Geral

A seção integridade fornece uma indicação visual da integridade da conexão do servidor do Skype for Business, do dispositivo de áudio, do dispositivo de vídeo, do estado de resiliência e do dispositivo de tela.

![Portal de administração do Lync System da sala integridade](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Anotações adicionais sobre o portal administrativo da Web

> [!NOTE]
>  As alterações de configuração são aplicadas somente após o sistema SRS ser reiniciado. > se a senha da conta do LRSApp expirar, você não poderá ver o status das salas. Configure a senha da conta do LRSAppuser para que ela nunca expire ou atualize a senha quando ela estiver próxima de expiração. > o portal da Web administrativo do SRS só tem suporte para implantações locais.

### <a name="bulk-management"></a>Gerenciamento em massa

O gerenciamento em massa de salas SRS é um recurso projetado para administradores de ti avançados, simplificar o fluxo de trabalho e habilitá-los com uma ferramenta conveniente que economiza tempo para gerenciar remotamente várias salas de maneira em massa.

Para ver essa funcionalidade, o usuário precisa ser provisionado como membro do grupo de segurança especial, **LRSPowerUserAdminsGroup**.

Não há limite quanto ao número de salas SRS que você pode selecionar para gerenciamento em massa. No entanto, você só pode executar uma operação de gerenciamento em massa de cada vez.

Para executar uma operação de gerenciamento em massa, selecione as salas que você deseja monitorar e clique no menu gerenciamento em massa.

### <a name="frequently-asked-questions"></a>Perguntas frequentes

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Por que não consigo me conectar ao portal administrativo da Web?

Ao abrir https://localhost/lrs, você poderá ver a página de entrada, mas quando digitar as suas credenciais, não poderá se conectar. Nesse caso, você deve abrir https://FQDNofFEserver/SRS para entrar no portal administrativo da Web.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Por que não consigo ver o SRS v1 no portal da Web administrativo?

- Verifique se você tem contas do SRS em sua implantação e se elas são criadas de acordo com as recomendações de implantação do portal de Web administrativo do SRS. Certifique-se de que as contas do SRS sejam provisionadas usando enable-CsMeetingRoom, not Enable-CsUser, no servidor do Skype for Business.

- Se você tiver criado contas do SRS e não conseguir ver as contas no portal administrativo da Web, colete os logs do servidor usando a ferramenta de log do Skype for Business Server com o componente **MeetingPortal** selecionado e, em seguida, envie-os para o contato de suporte do SRS.

- Se você tiver criado contas do SRS e não conseguir ver as contas no portal administrativo da Web, colete os logs do cliente usando o Fiddler e também copie o log do console das ferramentas de desenvolvimento do navegador e envie-os para o contato de suporte do SRS. Você também pode modificar o valor de nível de rastreamento no Web. config para obter um log mais detalhado.

  ```
  <system.diagnostics>
    <switches>
      <!--
      This switch controls logging message levels. 0 implies
      logging is turned off. 1 implies only errors are logged,
      2 implies errors &amp; warnings. 4 is the most detailed.
      -->
      <add name="TraceLevelSwitch" value="3" />
    </switches>
  </system.diagnostics>
  ```

#### <a name="why-cant-i-see-the-status-of-srs-in-the-administrative-web-portal"></a>Por que não consigo ver o status do SRS no portal da Web administrativo?

- Certifique-se de que a conta de usuário do LRSApp seja compatível com SIP.

- Se você ainda estiver com problemas, colete o arquivo **trace. log** no sistema SRS de D:\Tracing\LRSAdminLogs\, e envie-o para o contato de suporte do SRS.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Por que não consigo ver os menus de gerenciamento em massa do SRS no portal administrativo da Web?

Verifique se a conta de usuário do LRSApp está habilitada para SIP e faz parte do grupo de segurança LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>O portal da Web administrativo do SRS v1 funciona com salas do Microsoft Teams?

Não.


