---
title: Solucionar problemas de instalação e atualização do Microsoft Teams no Windows
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: lenatarhun
ms.topic: article
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: high
search.appverid: MET150
description: Saiba como solucionar problemas de instalação e atualização para o aplicativo cliente de área de trabalho do Teams no Windows.
ms.openlocfilehash: beed5767c459e4f758af002ce881c8490d5cff16
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62401165"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Solucionar problemas de instalação e atualização do Microsoft Teams no Windows

Este artigo fornece orientação sobre como diagnosticar e solucionar problemas de instalação e atualização para o aplicativo cliente do Teams que está sendo executado no Windows.

## <a name="check-whether-teams-is-updated-successfully"></a>Verificar se o Teams foi atualizado com êxito

Siga estas etapas para verificar se uma atualização do Teams foi instalada com êxito.

1. No Teams, selecione a sua imagem de perfil e, em seguida, clique em **Sobre a** > **Versão**.
2. No mesmo menu, clique em **Verificar se há Atualizações**.
3. Aguarde a faixa na parte superior do aplicativo para indicar que uma "atualização" do Teams é necessária. O link deve ser mostrado cerca de um minuto depois, pois esse processo baixa a nova versão do Teams. A faixa também permite que você saiba se você já está executando a versão mais recente, ou seja, se não é necessário atualizar.
4. Clique no link atualizar na faixa.
5. Aguarde até que o Teams seja reiniciado e, em seguida, repita a etapa 1 para ver se o aplicativo foi atualizado.

Se você vir uma mensagem de falha ou se o número da versão for igual ao da etapa 4, o processo de atualização falhou.

## <a name="troubleshoot-installation-and-update-issues"></a>Solucionar problemas de instalação e atualização

### <a name="troubleshoot-installation-issues"></a>Solucionar problemas de instalação

Quando o Teams é instalado, o instalador da equipe registra a sequência de eventos em %LocalAppData%\SquirrelTemp\SquirrelSetup.log. A primeira coisa a procurar é uma mensagem de erro ou uma pilha de chamadas próxima ao final do log. Observe que as pilhas de chamadas no início do log podem não significar que há um problema de instalação. Pode ser mais fácil comparar seu log com o log de uma instalação bem-sucedida (mesmo em outro computador) para ver o que é esperado.

Se o SquirrelSetup.log não indicar a causa ou se você precisar de mais informações para solucionar o problema, confira [Coletar e analisar logs de aplicativos e sistemas](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>Solucionar problemas de atualização

Quando o Teams é instalado com êxito, o local do log alterna de %LocalAppData%\SquirrelTemp para %LocalAppData%\Microsoft\Teams. Neste local, há dois arquivos de log de interesse, SquirrelSetup.log e logs.txt.

- O arquivo SquirrelSetup.log neste local é escrito por Update.exe, que é um executável que usa o aplicativo Teams.
- O arquivo Logs.txt é usado pelo aplicativo Teams (especificamente Teams.exe) para registrar eventos significativos do aplicativo. Ele provavelmente conterá informações de falha.

Esses arquivos de log contêm informações de identificação pessoal (PII) e, portanto, não são enviados para a Microsoft.

O Teams pode iniciar o processo de atualização automaticamente (dependendo da política) ou os usuários podem verificar manualmente se há atualizações acessando a imagem de perfil > **Verifique se há atualizações**. Os dois métodos usam a seguinte sequência de eventos.

1. **Verifique se há atualizações**. O Teams faz uma solicitação na Web e incluo informações sobre a versão atual do aplicativo e o toque de implantação. O objetivo desta etapa é obter o link de download. Uma falha nesta etapa faz logon no logs.txt.
2. **Baixar a atualização**. O Teams baixa a atualização usando o link de download obtido na etapa 1. Quando o download estiver concluído, o Teams chama Update.exe para testar o download. Uma falha de download também está conectada em logs.txt.
3. **Testar a atualização**. O conteúdo baixado é verificado e desempacotado em uma pasta intermediária,%LocalAppData%\Microsoft\Teams\stage), que é feito por Update.exe. As falhas nesta etapa são registradas em SquirrelTemp.log.
4. **Instalar a atualização**. Há várias maneiras de iniciar o Teams. O sistema inicia automaticamente o Teams quando um usuário faz logon ou você pode iniciar o Teams por meio de um atalho. Nesta etapa, Update.exe verifica a presença da pasta de preparação, verifica o conteúdo novamente e realiza operações de arquivo para reativar o aplicativo. O backup da pasta antigo do aplicativo no %LocalAppData%\Microsoft\Teams\current é feito em %LocalAppData%\Microsoft\Teams\previous e a pasta do estágio é renomeada para "atual". As falhas nesta etapa são registradas em SquirrelTemp.log.

Se SquirrelTemp.log ou logs.txt não contiverem informações suficientes para determinar a causa subjacente, e você precisar de mais informações para solucionar o problema, vá para [Coletar e analisar os logs de aplicativos e sistemas](#collect-and-analyze-application-and-system-logs).

## <a name="collect-and-analyze-application-and-system-logs"></a>Coletar e analisar logs de aplicativos e do sistema

Esta seção descreve como coletar e analisar os logs do aplicativo e do sistema para obter informações mais abrangentes e solucionar o problema. Você usará as ferramentas do Sysinternals para concluir essas etapas. Para saber mais, confira [Windows Sysinternals](/sysinternals/).

### <a name="collect-logs"></a>Colete os logs

1. Baixe [ferramentas Sysinternals](https://download.sysinternals.com/files/SysinternalsSuite.zip).
2. Extraia o arquivo zip para a pasta %TEMP% na unidade local.
3. Abra um prompt de comando elevado e siga este procedimento:

    1. Execute o seguinte procedimento para ir para a pasta TEMP:

        ```console
        cd /d %TEMP%
        ```
    2. Copie a instalação e os logs do aplicativo. Observe que, dependendo do ponto de falha, alguns desses logs podem não estar presentes.

        ```console
        copy %LocalAppData%\SquirrelTemp\SquirrelSetup.log SquirrelSetup.log
        copy %AppData%\Microsoft\Teams\logs.txt logs.txt
        copy %LocalAppData%\Microsoft\Teams\SquirrelSetup.log SquirrelSetup_Teams.log
        ```
    3. Execute o seguinte procedimento para capturar as alças de abertura.

        ```console
        handle > handles.txt
        ```

    4. Execute o seguinte para capturar as DLLs abertas.

        ```console
        listdlls -v Teams > dlls.txt
        ```
    5. Execute o seguinte procedimento para capturar os drivers que estão em execução.

        ```console
        driverquery /v > driverquery.txt
        ```

    6. Execute o seguinte para capturar as ACLs (listas de controle de acesso) da pasta do Teams.

        ```console 
        icacls %LOCALAPPDATA%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Analisar logs (para usuários avançados)

Uma atualização com falha poderá resultar em um comportamento de aplicativo imprevisível. Por exemplo, os usuários podem não conseguir sair do Teams, ter uma versão obsoleta do Teams ou não conseguem iniciar o Teams. Se você tiver um problema durante uma atualização, o primeiro local a ser pesquisado será o SquirrelTemp.log. Estes são os diferentes tipos de falhas de atualização, listados do mais comum para a menos comum e como analisar e solucionar problemas usando logs.

#### <a name="unable-to-exit-teams"></a>Não é possível sair do Teams

À medida que o Teams determina se precisa ser atualizado para uma versão mais recente, ele baixa e prepara o novo aplicativo e aguarda a oportunidade para reiniciar da próxima vez que o computador estiver ocioso. Um problema comum durante esse processo é quando outro processo ou um driver de sistema de arquivos bloqueia o processo Teams.exe, o que impede que o Teams.exe saia. Como resultado, o aplicativo Teams não pode ser substituído pelos aplicativos testados e recentemente baixados.

Dicas de solução de problemas:

- Para confirmar que este é o problema que você está enfrentando, encerre o Teams (clique com o botão direito do mouse no Teams na barra de tarefas e clique em **Sair**). Em seguida, abra o Gerenciador de tarefas do Windows para ver se uma instância do Teams ainda está sendo executada.  
- Se você não estiver no computador que está com esse problema, inspecione o SquirrelTemp.log coletado no computador que está enfrentando esse problema e procure a entrada "programa: não é possível finalizar o processo no log".
- Para determinar o que está impedindo que o Teams.exe saia, examine os logs DLLs.txt e Handles.txt. Eles te informarão quais são os processos que impedem a saída do Teams.
- Outro culpado que pode impedir a saída do Teams é o driver de filtro do sistema de arquivos no modo kernel. Use a ferramenta SysInternals, [ProcDump](/sysinternals/downloads/procdump), para coletar o despejo de processo no modo kernel executando ```procdump -mk <pid>```, onde \<pid> é o ID do processo obtido no Gerenciador de tarefas. Você também pode verificar o arquivo de log DRIVERQUERY. txt para ver os drivers de filtro ativo que podem interferir com o Teams.
- Para recuperar esse Estado, reinicie o computador.

#### <a name="file-permissions"></a>Permissões de arquivo

O Teams cria várias subpastas e arquivos no perfil do usuário durante todo o processo de instalação e atualização. Como o aplicativo e o atualizador são executados como usuário não privilegiado, as permissões de leitura e gravação devem ser concedidas nas seguintes pastas:

|Pasta  |Usada por  |
|---------|---------|
|%LocalAppData%\SquirrelTemp     | Instalador do Teams (por exemplo, Teams_Windows_x64. exe) durante a fase de instalação        |
|%LocalAppData%\Microsoft\Teams  | Atualizador do Teams (Update. exe) para extrair e testar o pacote do aplicativo durante o processo de atualização        |
|%AppData%\Microsoft\Teams   |  Aplicativo Teams (Teams.exe) para salvar as configurações, os Estados do aplicativo e o pacote de atualização baixado (pré-configurado)       |

Se o Teams tiver o acesso negado porque não é possível gravar em um arquivo, outro aplicativo pode estar interferindo ou uma entrada de descritor de segurança pode estar limitando o acesso de gravação a uma pasta.

Dicas de solução de problemas:

- Procure por evidências de "acesso negado" em SquirrelTemp.log ou logs.txt. Verifique esses arquivos para ver se houve uma tentativa de gravação em um arquivo que falhou.
- Abra icacls.txt e procure a entrada de controle de acesso (ACE) efetiva que bloqueia operações de gravação por um usuário que não é um administrador. Geralmente, isso se encontra em uma das entradas da DACL. Para obter mais informações, consulte a documentação [icacls](/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>Arquivo corrompido

Em alguns casos, o software de criptografia pode alterar os arquivos na pasta %LocalAppData%\Microsoft\Teams, o que pode impedir a inicialização do Teams. Isso pode acontecer a qualquer momento, mesmo quando o aplicativo não está sendo atualizado. Infelizmente, quando um arquivo está corrompido, a única maneira de recuperar esse estado é desinstalar e reinstalar o Teams.

> [!NOTE]
> Se você não conseguir determinar a causa do problema, usando uma das seguintes etapas, talvez você queira experimentar uma sessão de [Process Monitor](/sysinternals/downloads/procmon). O Process Monitor é uma ferramenta Sysinternals que registra o acesso ao registro e ao sistema de arquivos.

## <a name="related-topics"></a>Tópicos relacionados

- [Obter clientes para o Teams](get-clients.md)
- [Atualizações de cliente do Teams](teams-client-update.md)
- [Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
