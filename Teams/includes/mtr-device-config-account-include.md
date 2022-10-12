
Cada Salas do Microsoft Teams precisa de sua própria conta de recurso. A conta de recurso é a conta na qual Salas do Teams dispositivo faz logon e é o que os usuários em sua organização convidam para reservar a Sala do Teams.

Ao criar a caixa de correio de recurso, você pode especificar se deseja permitir reuniões recorrentes, fazer com que a sala aceite automaticamente convites, quantos dias no futuro aceitar convites e assim por diante.

> [!TIP]
> Ao nomear suas contas de recurso, recomendamos usar uma convenção de nomenclatura padrão para o início do endereço de email. Isso ajudará na criação de grupos dinâmicos para facilitar o gerenciamento no Azure Active Directory. Por exemplo, você pode usar "mtr-" para todas as contas de recursos que serão associadas a Salas do Microsoft Teams.

> [!TIP]
> Recomendamos que você crie todas as contas de recursos usando o Exchange Online e o Azure Active Directory.

Crie uma conta de recurso usando um método de uma das seguintes guias:

#### <a name="in-microsoft-365-admin-center"></a>[**Em Centro de administração do Microsoft 365**](#tab/m365-admin-center)

1. Acesse o Centro de administração do Microsoft 365.

2. Forneça as credenciais de administrador para seu locatário do Microsoft 365.

3. Vá para **Recursos** no painel esquerdo e selecione Salas **& equipamento**. Se essas opções não estiverem disponíveis no painel esquerdo, talvez seja necessário selecionar **Mostrar tudo** primeiro.

4. Selecione **Adicionar recurso** para criar uma nova conta de recurso. Insira um nome de exibição e um endereço de email para a conta e selecione **Salvar**.

5. Por padrão, as contas de recurso são definidas com as seguintes configurações:

    - Permitir reuniões repetidas
    - Recusar reuniões automaticamente fora dos limites a seguir
      - Janela de reserva (dias): 180
      - Duração máxima (horas): 24
    - Aceitar automaticamente solicitações de reunião

    Se você quiser alterá-las, selecione **Editar opções de reserva** antes de selecionar **Fechar**. Se você quiser alterá-los mais tarde, vá  >  para Salas de Recursos **& equipamento**, selecione a conta de recurso. Em Seguida, **em Opções de Reserva**, selecione **Editar**.

6. Vá para **Usuários** > **Ativos e** selecione a sala que você criou para abrir o painel de propriedades.

7. Em seguida, atribua uma senha à conta de recurso. No painel, selecione **Redefinir senha**.

8. Exigir que os usuários alterem a senha em um dispositivo compartilhado causará problemas de entrada. **Desmarque Exigir que esse usuário altere a senha** ao entrar pela primeira vez e selecione **Redefinir senha**.

Talvez você também precise aplicar políticas de largura de banda ou políticas de reunião a essa conta. Você pode definir políticas de caixa de correio em uma etapa posterior.

#### <a name="with-exchange-online"></a>[**Com Exchange Online**](#tab/exchange-online)

1. Conecte-se [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

    ``` PowerShell
    Connect-ExchangeOnline
    ```

2. Por padrão, as caixas de correio de sala não têm contas associadas. Adicione uma conta ao criar uma caixa de correio de sala para que ela possa ser autenticada com o Microsoft Teams.

    Se você estiver criando uma nova caixa de correio de recurso:

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias <string> -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
    ```

    Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

    - Conta: ConferenceRoom01@contoso.com

    - Nome: ConferenceRoom01

    - Alias: ConferenceRoom01

    - Senha da conta: P@$$W 0rd5959

    ``` PowerShell
    New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
    ```

Se você estiver em uma configuração híbrida do Exchange, precisará adicionar um endereço de email para sua conta de domínio local. Consulte [Sincronizar diretórios de contas de usuário Office 365 locais e locais](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) para obter mais informações.

#### <a name="with-exchange-server"></a>[**Com Exchange Server**](#tab/exchange-server)

  1. Conecte-se ao Shell de Gerenciamento do Exchange. [Abra o Shell de Gerenciamento do Exchange](/powershell/exchange/exchange-server/open-the-exchange-management-shell) ou [conecte-se ao servidor Exchange usando o PowerShell remoto](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell).

  2. Para criar uma nova caixa de correio de sala:

      ``` PowerShell
      New-Mailbox -UserPrincipalName <UPN> -Name <String> -Alias <String> -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
      ```

      Este exemplo cria uma nova caixa de correio de sala com as seguintes configurações:

      - Conta: ConferenceRoom01@contoso.com

      - Nome: ConferenceRoom01

      - Alias: ConferenceRoom01

      - Senha da conta: P@$$W 0rd5959

   ``` PowerShell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
   ```

#### <a name="modify-an-existing-exchange-room-mailbox"></a>[**Modificar uma caixa de correio de sala existente do Exchange**](#tab/existing-account)

Para modificar uma caixa de correio de sala existente para se tornar uma conta de recurso, use a seguinte sintaxe:

``` PowerShell
Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
```

Este exemplo habilita a conta para a caixa de correio de sala existente que tem o valor de alias ConferenceRoom02 e define a senha como 9898P@$$W 0rd.

``` PowerShell
Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
```

Se você estiver em uma configuração híbrida do Exchange, também precisará adicionar um endereço de email para sua conta de domínio local. Consulte [Sincronizar diretórios de contas de usuário Office 365 locais e locais](https://support.microsoft.com/topic/how-to-use-smtp-matching-to-match-on-premises-user-accounts-to-office-365-user-accounts-for-directory-synchronization-75673b94-e1b8-8a9e-c413-ee5a2a1a6a78) para obter mais informações.

Para obter informações detalhadas sobre sintaxe e parâmetro, consulte [New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox) e [Set-Mailbox](/powershell/module/exchange/mailboxes/set-mailbox).

> [!NOTE]
> Se você estiver criando essa conta para a Sala do Teams no Surface Hub, também deverá habilitar o ActiveSync nessa conta. Isso permitirá que você envie emails diretamente do Surface Hub, que você pode usar para recursos como o Whiteboard. Confira [a aplicação de políticas activeSync a contas de dispositivo (Surface Hub)](/surface-hub/apply-activesync-policies-for-surface-hub-device-accounts) para saber mais.

---

> [!IMPORTANT]
> Se você estiver usando apenas essa conta de recurso para reservar espaço e aceitar ou recusar convites automaticamente, você concluiu a configuração. Se você estiver usando essa conta de recurso para chamadas PSTN, consulte [licenças](../teams-add-on-licensing/microsoft-teams-add-on-licensing.md) de complemento do Microsoft Teams para determinar de qual licença ela precisa.
