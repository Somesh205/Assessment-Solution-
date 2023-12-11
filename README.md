# Assessment-Solution-
import pandas as pd

def generate_car_matrix(dataset_path):
    # Read the CSV file into a DataFrame
    df = pd.read_csv(dataset_path)

    # Pivot the DataFrame to create the desired matrix
    result_df = df.pivot(index='id_1', columns='id_2', values='car').fillna(0)

    # Set diagonal values to 0
    result_df.values[[range(result_df.shape[0])]*2] = 0

    return result_df

# Example usage
dataset_path = 'dataset-1.csv'
result_matrix = generate_car_matrix(dataset_path)

# Display the result matrix
print(result_matrix)
