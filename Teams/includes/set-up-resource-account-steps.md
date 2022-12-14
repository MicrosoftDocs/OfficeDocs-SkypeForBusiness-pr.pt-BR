No Microsoft Teams, uma conta de recurso é necessária para cada atendente automático ou fila de chamadas. Contas de recurso também podem ser atribuídas números de telefone. É assim que você atribui números de telefone a atendentes automáticos e filas de chamadas permitindo que os chamadores de fora do Teams cheguem à fila de atendimento automático ou de chamada.

Este artigo aborda como criar contas de recursos e prepará-las para uso com atendentes automáticos e filas de chamadas.

Antes de iniciar os procedimentos neste artigo, verifique se você fez as seguintes etapas:

- [Obter licenças da Conta de Recursos Telefonia do Microsoft Teams](#obtain-microsoft-teams-phone-resource-account-licenses)
- [Obter números de telefone](#obtain-phone-numbers)

> [!NOTE]
> As contas de recurso usadas para atendentes automáticos e filas de chamadas estão desabilitadas para entrar e devem permanecer assim. Chat e presença não estão disponíveis para essas contas.

### <a name="obtain-microsoft-teams-phone-resource-account-licenses"></a>Obter licenças da Conta de Recursos Telefonia do Microsoft Teams

Cada conta de recurso requer uma licença para trabalhar com atendentes automáticos e filas de chamadas, conhecidas como uma **licença Telefonia do Microsoft Teams Conta de Recursos**. As assinaturas com o Teams Phone obtêm automaticamente uma alocação gratuita de **licenças Telefonia do Microsoft Teams Conta de Recursos** e, se mais forem necessárias, Telefonia do Microsoft Teams licenças extras **da Conta de Recursos** poderão ser adquiridas. Para obter detalhes sobre como obter essas licenças, consulte [Telefonia do Microsoft Teams licenças da Conta de Recursos](../teams-add-on-licensing/virtual-user.md).

Abordamos como [atribuir a licença a uma conta de recurso mais adiante neste artigo](#assign-a-license).

Se você comprou **Telefonia do Teams Padrão** ou **o Teams Phone com** licenças de pacote de plano de chamada, as licenças **da Conta de Recursos do Teams Phone** já estão em sua conta.

Para ver se você já tem licenças da **Conta de Recursos do Teams Phone**, entre no [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339) usando uma conta com permissões de administrador global. Em seguida, vá para [Cobrança > Seus produtos](https://admin.microsoft.com/Adminportal/Home#/subscriptions). Se você tiver licenças da **Conta de Recursos do Teams Phone**, elas aparecerão como **Telefonia do Microsoft Teams Conta de Recursos**.

1. Abra o [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339) e entre com um usuário que é um administrador global. Geralmente, essa é a conta usada para se inscrever no Microsoft 365.
2. No painel de navegação à esquerda, acesse [**Complementos** de **Serviços** de Compra de Cobrança  > ](https://admin.microsoft.com/Adminportal/Home#/catalog)**Consulte todos os produtos de complementos**. >  > 
3. Role até o final para encontrar a licença **Telefonia do Microsoft Teams Conta de Recursos**. Selecione **Detalhes** e **compre**.
4. Na página de compra de licença, selecione o número de licenças desejadas. Você precisa de uma licença para cada atendente automático e fila de chamadas que planeja configurar. Recomendamos selecionar pelo menos cinco licenças para que você possa configurar facilmente mais atendentes automáticos e filas de chamadas no futuro sem precisar comprar mais licenças imediatamente.
5. Desmarque **a atribuição automática a todos os usuários sem licenças**.
6. Selecione **Verificar agora**.
7. Confirme seu pedido, selecione **Avançar** e, em seguida, **Faça o pedido**.

Não há custo zero, mas você ainda precisa seguir estas etapas para adquirir a licença.

### <a name="obtain-phone-numbers"></a>Obter números de telefone

Os números de telefone são opcionais para atendentes automáticos e filas de chamadas. Para qualquer atendente automático ou fila de chamadas que você deseja ser acessível diretamente por um número de telefone, você deve ter uma conta de recurso com um número de telefone associado.

As contas de recursos podem usar números de telefone gratuitos ou de pedágio. Você pode solicitar novos números ou portar números existentes de outra operadora.

Os números de telefone aceitáveis que podem ser aplicados a contas de recursos incluem:

- **Chamando números de serviço de Planos:** Para adquirir números de serviço com planos de chamada, consulte [Obtendo números de telefone de serviço](../getting-service-phone-numbers.md).
- **Números de roteamento direto:** Para adquirir números de Roteamento Direto, consulte [Habilitar usuários para Roteamento Direto](/microsoftteams/direct-routing-enable-users#configure-the-phone-number-and-enable-enterprise-voice).
- **Números do Operator Connect:** Para adquirir números do Operator Connect, consulte [Configurar o Operator Connect](/microsoftteams/operator-connect-configure#set-up-phone-numbers).

Para portar um número de outra operadora, consulte [Transferir números de telefone para o Teams](../phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

## <a name="create-a-resource-account"></a>Criar uma conta de recurso

Você pode criar uma conta de recurso no centro de administração do Teams.

1. Entre no [centro de administração do Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851). 
2. Expanda **Voz** e selecione **Contas de recurso**.
3. Selecione **Adicionar**.
4. No painel **Adicionar conta de recurso** , preencha **Nome de exibição**, **Nome de usuário** e o **tipo de conta de recurso**. O tipo de conta de recurso pode ser **o atendente automático** ou **a fila de chamadas**, dependendo de como você pretende usar essa conta de recurso.
5. Selecione **Salvar**.

## <a name="assign-a-license"></a>Atribuir uma licença

Para cada conta de recurso, você deve atribuir uma **licença Telefonia do Microsoft Teams Conta de Recursos**.

1. Entre no [Centro de administração do Microsoft 365](https://go.microsoft.com/fwlink/p/?linkid=2024339). 
2. Expanda **Usuários** e selecione **Usuários ativos**.
3. Selecione a conta de recurso à qual você deseja atribuir uma licença. O painel de usuário da conta de recurso será exibido.
4. Na guia **Licenças e Aplicativos**, em **Licenças**, selecione **Telefonia do Microsoft Teams Conta de Recursos**.
5. Selecione **Salvar alterações**.

## <a name="assign-a-phone-number"></a>Atribuir um número de telefone

Se você estiver planejando usar a conta de recurso com um atendente automático ou uma fila de chamadas que requer um número de telefone, atribua um número à conta de recursos.

1. Entre no [centro de administração do Teams](https://go.microsoft.com/fwlink/p/?linkid=2066851).
2. Expanda **Voz** e, em seguida, selecione **Página Contas de recursos** .
3. Selecione a conta de recurso à qual você deseja atribuir um número de telefone e **selecione Atribuir/desatribuir**.
4. Na lista suspensa **Tipo de número** de telefone, escolha o tipo de número que você deseja usar.
5. Na caixa **Número de telefone atribuído** , pesquise o número que você deseja usar e selecione **Adicionar**. Certifique-se de incluir o código do país (por exemplo, +1 250 555 0012).
6. Selecione **Salvar**.

Para atribuir um roteamento direto ou um número híbrido a uma conta de recurso, você precisa usar o PowerShell:

```powershell
Set-CsPhoneNumberAssignment -Identity aa-contoso_main@contoso64.net -PhoneNumber +19295550150 -PhoneNumberType DirectRouting
```
