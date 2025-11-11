# Open Source UI cookbook

1. Open web UI
- [official page](https://docs.openwebui.com/)
- [github](https://github.com/open-webui/open-webui)
- 사용
    ```bash
    docker pull ghcr.io/open-webui/open-webui:main

    docker run -d -p 3000:8080 -v open-webui:/app/backend/data --name open-webui ghcr.io/open-webui/open-webui:main
    ```

2. Chainlit
- [official page](https://docs.chainlit.io/get-started/overview)
- [github](https://github.com/Chainlit/chainlit)
- [cookbook](https://github.com/Chainlit/cookbook)
- 사용
    ```bash
    pip install chainlit
    chainlit hello
    ```

    ```python
    # demo.py
    import chainlit as cl


    @cl.step(type="tool")
    async def tool():
        # Fake tool
        await cl.sleep(2)
        return "Response from the tool!"


    @cl.on_message  # this function will be called every time a user inputs a message in the UI
    async def main(message: cl.Message):
        """
        This function is called every time a user inputs a message in the UI.
        It sends back an intermediate response from the tool, followed by the final answer.

        Args:
            message: The user's message.

        Returns:
            None.
        """


        # Call the tool
        tool_res = await tool()

        await cl.Message(content=tool_res).send()
    ```
    ```bash
    chainlit run demo.py -w
    ```
