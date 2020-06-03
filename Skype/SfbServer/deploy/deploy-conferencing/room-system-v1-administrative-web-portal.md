---
title: Implantar o portal da Web administrativo do SRS v1 no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 81822efa-2100-4017-a470-8a5b98c49522
ms.collection: M365-voice
description: O Skype for Business Server o Skype Room Systems V1 (SRS v1, anteriormente conhecido como sistema de salas do Lync) é um portal da Web que as organizações podem usar para manter suas salas de conferência do Skype Room Systems. Os administradores podem usar o portal da Web administrativo do SRS v1 para monitorar a integridade do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.
ms.openlocfilehash: d718adb60437fdd7e08724a5ba5fc48fa120425e
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "42045894"
---
# <a name="deploy-srs-v1-administrative-web-portal-in-skype-for-business-server"></a>Implantar o portal da Web administrativo do SRS v1 no Skype for Business Server

O Skype for Business Server o Skype Room Systems V1 (SRS v1, anteriormente conhecido como sistema de salas do Lync) é um portal da Web que as organizações podem usar para manter suas salas de conferência do Skype Room Systems. Os administradores podem usar o portal da Web administrativo do SRS v1 para monitorar a integridade do dispositivo, por exemplo, monitorando dispositivos de áudio/vídeo. Com esse portal, os administradores podem coletar remotamente informações de diagnóstico para monitorar a integridade da sala de conferência.

Para usar esse recurso, o portal da Web administrativo do SRS v1 precisa ser implantado em todos os servidores front-end do Skype for Business Server. Este guia fornece instruções para os administradores sobre como instalar e configurar o portal da Web administrativo do SRS. Destina-se a administradores que têm conhecimento da administração do Skype for Business Server e que têm direitos de usuário de administrador para modificar a topologia do Skype for Business Server.

Depois que o portal da Web administrativo do SRS v1 é implantado no servidor, os administradores podem verificar os dispositivos de status SRS v1 fazendo logon no site de seus próprios computadores ou laptops.

> [!IMPORTANT]
> Baixe o [portal da Web administrativo do Microsoft Skype Room Systems v1 para o Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).

Neste tópico:

- [Configurar seu ambiente para o portal da Web administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)

- [Instalar o portal da Web administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Install_SRS)

- [Usar o portal da Web administrativo do SRS](room-system-v1-administrative-web-portal.md#Use_Portal)

## <a name="configure-your-environment-for-the-srs-v1-administrative-web-portal"></a>Configurar seu ambiente para o portal da Web administrativo do SRS v1
<a name="Config_Env"> </a>

Para usar o portal da Web administrativo do SRS v1, será necessário instalar ou configurar os pré-requisitos a seguir.

> [!IMPORTANT]
> Se o servidor estiver configurado com autenticação Kerberos e NTLM e o SRS estiver em execução em um computador que não ingressou no domínio, a autenticação Kerberos falhará e o usuário não verá o status do SRS no portal administrativo. Para resolver esse problema, configure o servidor com autenticação NTLM ou autenticação NTLM e TLS-DSK (sem Kerberos) ou Ingresse o computador SRS no domínio.

1. Instale as atualizações cumulativas do Skype for Business Server na topologia do Skype for Business Server.

    Para obter a atualização ou ver o que está incluído nele, consulte [atualizações para o Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).

2. Criar um usuário do Active Directory habilitado para SIP.

    O portal da Web administrativo do SRS v1 usa essas credenciais para consultar informações do Skype for Business Server. O nome de usuário nos exemplos fornecidos é LRSApp.

3. Crie um grupo de segurança do Active Directory com o nome LRSSupportAdminGroup.

    Crie o grupo com o escopo de grupo como segurança global e tipo de grupo como segurança. Os usuários habilitados para SIP que forem adicionados a esse grupo serão autorizados a ver a lista de salas e executar certos comandos, como coletar logs.

4. Crie um grupo de segurança do Active Directory com o nome LRSFullAccessAdminGroup.

    Criar o grupo com escopo de grupo como global e tipo de grupo como Security. SIP habilitados para usuários que são adicionados a este grupo são autorizados a usar toda a funcionalidade do portal de administração em uma única sala do Skype. Para incluir suporte para gerenciamento em massa de salas do Skype, consulte a etapa 5.

     ![Lista de grupos de administração com a função de grupo de segurança](../../media/LRS_LRSFullAccessAdminGroup.png)

5. Crie um grupo de segurança do Active Directory com o nome LRSPowerUserAdminsGroup.

    Crie o grupo com o escopo de grupo como segurança global e tipo de grupo como segurança. Os usuários habilitados para SIP que são adicionados a esse grupo estão autorizados a usar toda a funcionalidade do portal de administração, incluindo o gerenciamento em massa de salas do Skype for Business.

6. Adicione LRSFullAccessAdminGroup como membro de LRSSupportAdminGroup.

     ![Página Membros de propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRSSupportAdminGroup.png)

7. Crie um usuário do Active Directory habilitado para SIP com o nome LRSSupport. Adicione este usuário ao LRSSupportAdminGroup.

     ![Página Membros de propriedades LRSSupportAdminGroup](../../media/LRS_Add_LRS_SIP_SupportUser.png)

8. Instale o [ASP.NET MVC 4 para o Visual Studio 2010 SP1 e o Visual Web developer 2010 SP1](https://go.microsoft.com/fwlink/p/?LinkId=323967).

## <a name="install-the-srs-v1-administrative-web-portal"></a>Instalar o portal da Web administrativo do SRS v1
<a name="Install_SRS"> </a>

Baixe o [portal da Web administrativo do Microsoft Skype Room Systems v1 para o Skype for Business Server 2015](https://www.microsoft.com/download/details.aspx?id=46906).

Para instalar o portal da Web administrativo do SRS v1, use as etapas a seguir.

1. Configure a porta de aplicativo confiável executando o seguinte cmdlet no Shell de gerenciamento do Skype for Business Server:

   ```powershell
   Set-CsWebServer -Identity POOLFQDN -MeetingRoomAdminPortalInternalListeningPort 4456 -MeetingRoomAdminPortalExternalListeningPort 4457
   ```

2. Para instalar o portal de sala de reunião, baixe o **MeetingRoomPortalInstaller. msi** e, em seguida, execute-o como administrador.

3. Abra o arquivo Web. config no seguinte local:

    % Program programas%\skype for Business Server 2015 \ Web Components\Meeting sala Portal\Int\Handler\

4. No arquivo Web. config, altere o PortalUserName para o nome de usuário criado na etapa 2, abaixo da seção "[configurar seu ambiente para o portal da Web administrativo do SRS v1](room-system-v1-administrative-web-portal.md#Config_Env)" (o nome recomendado na etapa é LRSApp):

    ```xml
    <add key="PortalUserName" value="sip:LRSApp@domain.com" />
    ```

5. Como o portal de administração do SRS v1 é um aplicativo confiável, você não precisa fornecer a senha na configuração do Portal. Se este usuário estiver usando um registrador diferente do registrador local, você precisará especificar o registrador para ele adicionando a seguinte linha no arquivo Web. config:

   ```xml
   <add key="PortalUserRegistrarFQDN" value="pool-xxxx.domain.com" />
   ```

6. Se a porta usada for diferente de 5061, adicione a seguinte linha no arquivo Web. config:

   ```xml
   <add key="PortalUserRegistrarPort" value="5061" />
   ```

### <a name="verify-installation-of-the-srs-administrative-web-portal"></a>Verificar a instalação do portal da Web administrativo do SRS

Para verificar a instalação do portal da Web administrativo do SRS v1, faça o seguinte:

1. Em um servidor front-end, navegue até a seguinte URL:

    https:// \<fe-server\> /lRS

    Você não verá nenhum erro, conforme mostrado na imagem a seguir:

     ![Tela de entrada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortalSignIn.png)

2. Se você não vir nenhum erro, tente acessar a seguinte URL de qualquer outro computador na topologia:

    https:// \<fe-server\> /lRS

    Para acessar a página, você precisará adicionar os registros DNS, conforme descrito em "[registros DNS necessários para entrada automática de cliente](https://go.microsoft.com/fwlink/p/?LinkId=318056)".

## <a name="use-the-srs-administrative-web-portal"></a>Usar o portal da Web administrativo do SRS
<a name="Use_Portal"> </a>

Depois de implantar o SRS no servidor, você pode verificar o status de todas as salas do SRS entrando no portal da Web administrativo do SRS V1 a partir de um navegador.

### <a name="sign-in"></a>Entrar

1. Navegue até a seguinte URL:

    https:// \<fe-server\> /lRS

2. Insira as credenciais para a conta LRSSupport ou uma conta que foi adicionada ao grupo de segurança LRSSupportAdminGroup.

![Tela de entrada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortalSignIn.png)

### <a name="srs-administrative-web-portal-summary-page"></a>Página de resumo do portal da Web administrativo do SRS

A página de resumo fornece as seguintes informações para todas as salas do SRS implantadas no servidor:

- **Marca** O nome personalizado que o administrador fornece à sala. A marca pode ser definida no portal clicando no nome da sala.

- **Health** O status de integridade da sala, que é derivado do status de integridade de agregação da sala, que é mostrado na seção integridade da página Configurações da sala.

- **Próxima reunião** A data e a hora em que a próxima reunião foi agendada.

- **Versão do SRS, fabricante, modelo** Esses valores são predefinidos no SRS. Dependendo do fabricante, esses campos podem ser deixados em branco.

- **Última atualização** Exibe a última vez em que a página da Web foi atualizada.

![Exibição resumida do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_Summary_view.png)

> [!NOTE]
> Você só verá o menu de gerenciamento em massa se fizer parte do grupo de segurança LRSPowerUserAdminsGroup.

### <a name="srs-room-information"></a>Informações de sala do SRS

A seção informações de sala do portal permite que você visualize e configure salas individuais do SRS. Ele contém quatro seções: configurações, detalhes, registro em log e integridade.

#### <a name="settings"></a>Configurações

Na seção Configurações, é possível definir a senha, a marca de sala e os níveis de volume padrão para a sala. Se você definir essas configurações, as alterações serão replicadas somente depois que você reiniciar o console do SRS. Você verá apenas as configurações de atualizações do sistema para dispositivos SRS usando a versão 15,12 e posteriores.

![Configurações de sala do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_RoomInfoSettings.png)

#### <a name="details"></a>Detalhes

A seção detalhes fornece um resumo somente leitura das configurações da sala SRS, incluindo: o horário da última atualização; próxima reunião; últimas atualizações, manutenção e calibração; configurações de alto-falante, MIC e campainha padrão; Version URI DO SIP; número de telas e detalhes sobre cada tela; status e atividade.

![Exibição detalhada do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_Detail_view.png)

#### <a name="troubleshooting"></a>Solução de problemas

A seção solução de problemas pode ser usada para coletar logs remotamente e salvá-los em um local especificado. Você também pode reiniciar o console do SRS (interface de usuário do SRS) ou reiniciar todo o sistema. Para coletar logs, forneça um caminho de pasta no formato especificado e certifique-se de que a pasta tenha permissões de gravação atribuídas à conta de máquina do SRS. Se o tamanho do log for muito grande, pode levar até 5 minutos para concluir a coleta de logs. A atualização da página fornecerá o status mais recente.

#### <a name="health"></a>Integridade

A seção de integridade fornece uma indicação visual da integridade da conexão do Skype for Business Server, dispositivo de áudio, dispositivo de vídeo, estado de resiliência e dispositivo de tela.

![Integridade da sala do portal de administração do sistema de salas do Lync](../../media/LRS_AdminPortal_RoomInfoHealth.png)

### <a name="additional-notes-about-the-administrative-web-portal"></a>Observações adicionais sobre o portal da Web administrativo

> [!NOTE]
>  As alterações de configuração são aplicadas somente depois que o sistema SRS é reiniciado. > se a senha da conta LRSApp expirar, não será possível ver o status das salas. Configure a senha da conta LRSAppuser para que ela nunca expire ou atualize a senha quando ela estiver prestes a expirar. > o portal da Web administrativo do SRS tem suporte apenas para implantações locais.

### <a name="bulk-management"></a>Gerenciamento em massa

O gerenciamento em massa de salas do SRS é um recurso projetado para administradores de ti avançados, para simplificar o fluxo de trabalho e habilitá-lo com uma ferramenta conveniente que economiza tempo para gerenciar remotamente várias salas de maneira em massa.

Para ver essa funcionalidade, o usuário precisa ser provisionado como um membro do grupo de segurança especial, **LRSPowerUserAdminsGroup**.

Não há limite para o número de salas SRS que você pode selecionar para gerenciamento em massa. No entanto, você só pode executar uma operação de gerenciamento em massa por vez.

Para executar uma operação de gerenciamento em massa, selecione as salas que você deseja monitorar e clique no menu de gerenciamento em massa.

### <a name="frequently-asked-questions"></a>Perguntas frequentes

#### <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>Por que não consigo entrar no portal da Web administrativo?

Ao abrir https://localhost/lrs o, você poderá ver a página de entrada, mas quando digitar suas credenciais, não poderá entrar. Nesse caso, você deve abrir https://FQDNofFEserver/SRS o para entrar no portal da Web administrativo.

#### <a name="why-cant-i-see-srs-v1-in-the-administrative-web-portal"></a>Por que não consigo ver o SRS v1 no portal da Web administrativo?

- Verifique se você tem contas do SRS em sua implantação e se elas foram criadas de acordo com as recomendações de implantação do portal da Web administrativo do SRS. Verifique se as contas do SRS estão provisionadas usando o Enable-CsMeetingRoom, não o Enable-CsUser, no Skype for Business Server.

- Se você tiver criado contas do SRS e não puder ver as contas no portal da Web administrativo, colete os logs do servidor usando a ferramenta de log do Skype for Business Server com o componente **MeetingPortal** selecionado e, em seguida, envie-os para o contato de suporte do SRS.

- Se você tiver criado contas do SRS e não puder ver as contas no portal da Web administrativo, colete os logs do cliente usando Fiddler e também copie o log do console das ferramentas de desenvolvimento do navegador e, em seguida, envie-os para o contato de suporte do SRS. Você também pode modificar o valor de nível de rastreamento no Web. config para obter um log mais detalhado.

  ```xml
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

- Verifique se a conta de usuário LRSApp está habilitada para SIP.

- Se você ainda estiver com problemas, colete o arquivo **trace. log** no sistema SRS de D:\Tracing\LRSAdminLogs \, e envie-o para seu contato de suporte do SRS.

#### <a name="why-cant-i-see-the-bulk-management-menus-for-srs-in-the-administrative-web-portal"></a>Por que não consigo ver os menus de gerenciamento em massa do SRS no portal da Web administrativo?

Verifique se a conta de usuário do LRSApp está habilitada para SIP e faz parte do grupo de segurança LRSPowerUserAdminsGroup.

#### <a name="does-the-srs-v1-administrative-web-portal-work-with-microsoft-teams-rooms"></a>O portal da Web administrativo do SRS v1 funciona com salas do Microsoft Teams?

Não.


