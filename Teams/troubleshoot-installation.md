---
title: Solucionar problemas de instalação e atualização do Microsoft Teams no Windows
ms.author: mikeplum
author: MikePlumleyMSFT
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
ms.openlocfilehash: d01c67c58a67ab0c52becdd54f0298ec0196704c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605850"
---
# <a name="troubleshoot-microsoft-teams-installation-and-update-issues-on-windows"></a>Solucionar problemas de instalação e atualização do Microsoft Teams no Windows

Este artigo fornece orientação sobre como diagnosticar e solucionar problemas de instalação e atualização para o aplicativo cliente do Teams que está sendo executado no Windows. Para obter informações adicionais sobre solução de problemas, consulte [solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams).

## <a name="check-whether-teams-is-updated-successfully"></a>Verificar se o Teams foi atualizado com êxito

Siga estas etapas para verificar se uma atualização do Teams foi instalada com êxito.

1. No Teams, selecione as reticências (**...**) ao lado da imagem do perfil e clique em **Sobre** > **Versão**. Aparecerá um banner que mostra sua versão Teams atual e quando foi atualizada pela última vez. Por exemplo **você tem o Microsoft Teams versão 1.5.00.3806 (64 bits)-E. Ele foi atualizado pela última vez em 16/02/2022**.
2. Abra o menu de reticências novamente e clique **Verificar se há atualizações**.
3. Aguarde a faixa na parte superior do aplicativo para indicar que uma "atualização" do Teams é necessária. O link deve ser mostrado cerca de um minuto depois, pois esse processo baixa a nova versão do Teams. A faixa também permite que você saiba se você já está executando a versão mais recente, ou seja, se não é necessário atualizar.
4. Clique no link atualizar na faixa.
5. Aguarde até que o Teams seja reiniciado e, em seguida, repita a etapa 1 para ver se o aplicativo foi atualizado.

Se você vir uma mensagem de falha ou se o número da versão for igual ao da etapa 4, o processo de atualização falhou.

## <a name="troubleshoot-installation-and-update-issues"></a>Solucionar problemas de instalação e atualização

### <a name="troubleshoot-installation-issues"></a>Solucionar problemas de instalação

Quando Teams é instalado, o Teams registra a sequência de eventos para `%LocalAppData%\SquirrelTemp\SquirrelSetup.log`. A primeira coisa a procurar é uma mensagem de erro ou uma pilha de chamadas próxima ao final do log. Observe que as pilhas de chamadas no início do log podem não significar que há um problema de instalação. Pode ser mais fácil comparar seu log com o log de uma instalação bem-sucedida (mesmo em outro computador) para ver o que é esperado.

Se `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` não indicar a causa ou se você precisar de mais informações para solucionar o problema, consulte [Coletar e analisar logs do aplicativo e do sistema](#collect-and-analyze-application-and-system-logs).

### <a name="troubleshoot-update-issues"></a>Solucionar problemas de atualização

Quando Teams é instalado com êxito, o local do log alterna de `%LocalAppData%\SquirrelTemp` para `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log`. Outro arquivo de log de interesse é `%AppData%\Microsoft\Teams\logs.txt`.

- O `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log` arquivo é escrito por `Update.exe`, que é um executável que fornece serviços ao aplicativo Teams.
- O `%AppData%\Microsoft\Teams\logs.txt` arquivo é usado pelo aplicativo Teams (especificamente `Teams.exe`) para registrar eventos significativos do aplicativo. Provavelmente, contém informações de falha.

Esses arquivos de log contêm informações de identificação pessoal (PII) para que eles não são enviados à Microsoft.

O Teams pode iniciar automaticamente o processo de atualização (dependendo da política) ou os usuários podem verificar manualmente se há atualizações acessando o menu de reticências (**...**) ao lado de sua imagem de perfil e selecionando **Verificar se há atualizações**. Os dois métodos usam a seguinte sequência de eventos.

1. **Verifique se há atualizações**. O Teams faz uma solicitação na Web e incluo informações sobre a versão atual do aplicativo e o toque de implantação. O objetivo desta etapa é obter o link de download. Uma falha nesta etapa é registrada em `%AppData%\Microsoft\Teams\logs.txt`.
2. **Baixar a atualização**. O Teams baixa a atualização usando o link de download obtido na etapa 1. Quando o download for concluído, o Teams chama `Update.exe` para preparar o download. Uma falha de download também está registrada em `%AppData%\Microsoft\Teams\logs.txt`.
3. **Testar a atualização**. O conteúdo baixado é verificado e descompactado em uma pasta intermediária, `%LocalAppData%\Microsoft\Teams\stage`), que é feita por `Update.exe`. Falhas nesta etapa são registradas em `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log`.
4. **Instalar a atualização**. Há várias maneiras de iniciar o Teams. O sistema inicia automaticamente o Teams quando um usuário faz logon ou você pode iniciar o Teams por meio de um atalho. Nesta etapa, `Update.exe` verifica a presença da pasta de preparação, verifica o conteúdo novamente e executa operações de arquivo para desem estágio do aplicativo. A pasta de aplicativo antigo em `%LocalAppData%\Microsoft\Teams\current` é respaldada para `%LocalAppData%\Microsoft\Teams\previous` e a pasta de estágio é renomeada para `current`. Falhas nesta etapa são registradas em `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log`.

Se `%LocalAppData%\Microsoft\Teams\SquirrelSetup.log` ou `%AppData%\Microsoft\Teams\logs.txt` não contiverem informações suficientes para determinar a causa subjacente e você precisar de mais informações para solucionar o problema, acesse [Coletar e analisar logs de aplicativos e do sistema](#collect-and-analyze-application-and-system-logs).

## <a name="collect-and-analyze-application-and-system-logs"></a>Coletar e analisar logs de aplicativos e do sistema

Esta seção descreve como coletar e analisar os logs do aplicativo e do sistema para obter informações mais abrangentes e solucionar o problema. Você usará as ferramentas do Sysinternals para concluir essas etapas. Para saber mais, confira [Windows Sysinternals](/sysinternals/).

### <a name="collect-logs"></a>Colete os logs

1. Baixe [ferramentas Sysinternals](https://download.sysinternals.com/files/SysinternalsSuite.zip).
2. Extraia o arquivo zip para a pasta `%Temp%` em sua unidade local.
3. Abra um prompt de comando elevado e siga este procedimento:

    1. Execute o seguinte para ir para sua pasta `%Temp%`:

        ```console
        cd /d %Temp%
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
        icacls %LocalAppData%\Microsoft\Teams /save icacls.txt /T
        ```

### <a name="analyze-logs-for-advanced-users"></a>Analisar logs (para usuários avançados)

Uma atualização com falha poderá resultar em um comportamento de aplicativo imprevisível. Por exemplo, os usuários podem não conseguir sair do Teams, ter uma versão obsoleta do Teams ou não conseguem iniciar o Teams. Se você tiver um problema durante uma atualização, o primeiro lugar para procurar encontrar a causa é `%LocalAppData%\SquirrelTemp\SquirrelSetup.log`. Estes são os diferentes tipos de falhas de atualização, listados do mais comum para a menos comum e como analisar e solucionar problemas usando logs.

#### <a name="unable-to-exit-teams"></a>Não é possível sair do Teams

À medida que o Teams determina se precisa ser atualizado para uma versão mais recente, ele baixa e prepara o novo aplicativo e aguarda a oportunidade para reiniciar da próxima vez que o computador estiver ocioso. Um problema comum durante esse processo é quando outro processo ou um driver do sistema de arquivos bloqueia o processo do `Teams.exe`, o que impede a saída do `Teams.exe`. Como resultado, o aplicativo Teams não pode ser substituído pelos aplicativos testados e recentemente baixados.

Dicas de solução de problemas:

- Para confirmar que este é o problema que você está enfrentando, encerre o Teams (clique com o botão direito do mouse no Teams na barra de tarefas e clique em **Sair**). Em seguida, abra o Gerenciador de tarefas do Windows para ver se uma instância do Teams ainda está sendo executada.  
- ’Se você não estiver no computador que está tendo esse problema, inspecione o `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` coletado do computador que está enfrentando esse problema e procure um programa **: não é possível encerrar o processo** na entrada de log.
- Para determinar o que está impedindo `Teams.exe` de sair, `Dlls.txt` `Handles.txt` veja os logs criados na seção [Coletar logs](#collect-logs). Eles te informarão quais são os processos que impedem a saída do Teams.
- Outro culpado que pode impedir a saída do Teams é o driver de filtro do sistema de arquivos no modo kernel. Use a ferramenta SysInternals, [ProcDump](/sysinternals/downloads/procdump), para coletar o despejo de processo no modo kernel executando `procdump -mk <pid>`, onde \<pid> é o ID do processo obtido no Gerenciador de tarefas. Você também pode inspecionar o arquivo de log `Driverquery.txt` para ver os drivers de filtro ativos que podem interferir no Teams.
- Para recuperar esse Estado, reinicie o computador.

#### <a name="file-permissions"></a>Permissões de arquivo

O Teams cria várias subpastas e arquivos no perfil do usuário durante todo o processo de instalação e atualização. Como o aplicativo e o atualizador são executados como um usuário não elevado, as permissões de leitura e gravação devem ser concedidas nas seguintes pastas:

|Pasta  |Usada por  |
|---------|---------|
|`%LocalAppData%\SquirrelTemp`    | Instalador do Teams (por exemplo, `Teams_Windows_x64.exe`) durante a fase de instalação        |
|`%LocalAppData%\Microsoft\Teams`  | Atualizador do Teams (`Update.exe`) para extrair e preparar o pacote do aplicativo durante o processo de atualização        |
|`%AppData%\Microsoft\Teams`   |  Aplicativo Teams (`Teams.exe`) para salvar configurações, estados de aplicativo e o pacote de atualização baixado (pré-preparado)       |

Se o Teams tiver o acesso negado porque não é possível gravar em um arquivo, outro aplicativo pode estar interferindo ou uma entrada de descritor de segurança pode estar limitando o acesso de gravação a uma pasta.

Dicas de solução de problemas:

- Procure por `access denied` evidências em `%LocalAppData%\SquirrelTemp\SquirrelSetup.log` ou `%AppData%\Microsoft\Teams\logs.txt`. Verifique esses arquivos para ver se houve uma tentativa de gravação em um arquivo que falhou.
- Abra `Icacls.txt` e procure a entrada efetiva de controle de acesso (ACE) que bloqueia as operações de gravação por um usuário que não seja um administrador. Normalmente, isso está em uma das entradas da DACL. Para obter mais informações, consulte a documentação [icacls](/windows-server/administration/windows-commands/icacls).

#### <a name="file-corrupted"></a>Arquivo corrompido

Em alguns casos, o software de criptografia pode alterar arquivos na pasta `%LocalAppData%\Microsoft\Teams`, o que pode impedir o Teams de iniciar. Isso pode acontecer a qualquer momento, mesmo quando o aplicativo não está sendo atualizado. Quando um arquivo é corrompido, a única maneira de recuperar desse estado é desinstalar e reinstalar Teams.

> [!NOTE]
> Se você não conseguir determinar a causa do problema, usando uma das seguintes etapas, talvez você queira experimentar uma sessão de [Process Monitor](/sysinternals/downloads/procmon). O Process Monitor é uma ferramenta Sysinternals que registra o acesso ao registro e ao sistema de arquivos.

## <a name="related-topics"></a>Tópicos relacionados

- [Obter clientes para o Microsoft Teams](get-clients.md)
- [Atualizações de cliente do Teams](teams-client-update.md)
- [Solução de problemas do Teams](/MicrosoftTeams/troubleshoot/teams)
