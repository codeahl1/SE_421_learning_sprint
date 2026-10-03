# Reflection

I built an integer overflow visualization to better understand how storing numbers with a limited number of bits affects arithmetic. Before this project, I understood that integers had limits, but I wasn’t completely sure how those limits connected to the binary values stored in memory.

AI helped me come up with the basic format of the app, but I was responsible for the logic and testing the application thoroughly. My workflow involved saving the files locally, opening the app in a browser, reviewing the code, and trying different inputs. I focused on checking values near the limits and making sure the calculations, binary displays, and overflow messages matched.

One example that helped explain the concept was unsigned 8-bit addition: 255 + 1 wraps around to 0. The mathematical answer is 256, but that number cannot fit into eight bits. Seeing the bit pattern made it easier to understand why the stored result differs from the mathematical answer.

The app also helped me understand how the same bits can represent different numbers. For example, "11111111" represents 255 as an unsigned number, but −1 when interpreted as signed two’s complement. Changing the interpretation showed me why knowing the number’s type matters.

One limitation is that the app intentionally simulates wrapping. Actual behavior depends on the programming language and data type. In particular, signed integer overflow in C and C++ is undefined behavior, so it does not necessarily behave like this visualization.

AI helped me get started with the layout so I could focus on understanding the logic and checking the app’s behavior. If I extended the app, I would add a prediction mode that asks learners to guess the result before revealing the answer and explaining it. This would make the app more engaging and help learners check their understanding.
